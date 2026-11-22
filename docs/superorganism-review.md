# superorganism-experiment: deep-dive review

Reviewed 22 Nov 2026 (Europe/Rome). Read-only review of the public repositories; nothing was pushed, commented or filed.
Evaluated against **full sovereignty**: no third party can read, stop, steer, or take the agent's assets. Five axes: privacy, custody, funding, continuity, independence from any single host/vendor. The five hard open problems are treated as engineering goals. (The earlier "accountable custody" framing was dropped at Aljaz's request.)

## 1. What it is

- `autonomica-xyz/superorganism-experiment` is a **public fork** (GPL-3.0) of `Tribler/superorganism-experiment`. Tribler is the Delft University of Technology (TU Delft) P2P lab led by Johan Pouwelse. The fork was created 5 Jul 2026 and contains **zero Autonomica commits**. It is 2 README-only commits behind upstream. Issues are disabled on the fork, and the fork has no PRs.
- Tagline: "Unstoppable by design, self-replicating, self-hosted, self-evolving, and human oversight with democratic governance. Well, that is our Utopian dream!"
- Thesis (README): a citizen-run "society" where people have full control, their own money and AI that serves them. Control comes through direct democratic voting. The system is a network of BitTorrent seedboxes that buy their own servers with Bitcoin and clone themselves.
- Explicit disclaimer: "throw-away code", "vibe code", "unstable and unmaintainable". The lab has a zero-AI policy for production Tribler code. The ideas are to be re-implemented properly under NWO funding (4.3M EUR, to 2032).
- Linked research: TwoStepDemocracy (arXiv 2606.25559), SurvivalRank, FuSST (Sybil detection thesis), SelfReplicate (Matei Dogariu MSc), DelftClaw (OpenClaw agent infra, BSc students, "needs integration"). Lineage goes back to Dollynator/CloudOmate (2016–2017).

## 2. Components and stack

Python 3.10+, PySide6 desktop GUI, py-ipv8 3.1.0 (Tribler's P2P overlay: no DNS, public-key peer IDs), libtorrent, bitcoinlib, Bitcoin Core RPC (regtest), SQLite, LightGBM/XGBoost/scikit-learn. CI is a manual (`workflow_dispatch`) Windows .exe build with cx_Freeze. There is no CI test run.

| Module | Lines (py, approx) | What it does | Status |
|---|---|---|---|
| `self_replication_service__mycelium/` | ~8.8k + sh | **Mycelium**: seedbox orchestrator on a VPS. A 6-hourly decision loop runs failsafe → top-up → spawn. It buys VPSes from SporeStack with BTC, generates the child's SSH key, BIP39 wallet and SporeStack token, deploys over SSH, passes an inheritance (40% default) and a mutated "caution trait" (Gaussian drift). It gossips "whoami" over IPv8 and auto-updates by `git pull` from GitHub | Most "agent-like" part. Mainnet by default (`BITCOIN_NETWORK=bitcoin`). Has an LXC + regtest + electrs local simulation. Write-ahead intent records for idempotent payments (good) |
| `democracy/` | ~5.2k | Issues → solution proposals → votes, gossiped over IPv8 (push/pull), SQLite. Funding pools: BTC assurance contracts with `ALL\|ANYONECANPAY` PSBT pledges paying a developer for a PR | Works on regtest. **Not wired to anything**: votes do not change what code nodes run |
| `authentication/` | ~1.4k | Ed25519 identity; registration commits SHA-256(label‖network‖pubkey) in a BTC tx (stake identity) and is verified over RPC; challenge-response login | Unit-tested. Testnet/regtest only ("ToDo move to mainnet") |
| `crowdsourced_learn_to_rank/` | ~11k + vendored ipv8 (1.9 MB) | SurvivalRank: LTR models compete; NDCG scores gossiped; decentralized multi-armed bandit culls losers | Research prototype |
| `two_graph_fusion_public/` | ~13.6k | FuSST Sybil detection (trust graph + behaviour graph, belief propagation) | Reference code, "not integrated" |
| `torrent_health_and_investment/` | ~1k | SwarmHealth GUI: CC torrent swarm health + seedbox fleet view | Prototype |
| `ui/` | ~144k (mostly generated Qt resources) | Desktop app: torrents, fleet, voting, "autoresearch" page | Prototype |

**Organization of "agents":** there are no LLM agents. The autonomous unit is a **seedbox node**: a tiny economic organism with a wallet, a lifespan (prepaid VPS days), reproduction (spawn when runway is above the threshold) and death (failsafe sweep). Coordination is gossip plus a peer registry. There are no roles or hierarchy. Holon-wise, each node is a whole (own wallet, keys, lifecycle) and a part (fleet). However, nothing at the fleet level (budget, policy, identity) composes upward. "Eternal Autoresearch" (Karpathy autoresearch / Darwin Gödel Machine) is aspirational, and it currently relies on paying human developers.

## 3. What works vs. stubs

- Ran `pytest tests/unit` in a venv: **377 passed in 0.63 s** (authentication, bitcoin RPC client, democracy community/gossip/funding). Integration tests need bitcoind regtest, which was not available in the review environment, so they were not run. Mycelium has **no unit tests**; only the LXC simulation exists. Nothing was deployed and nothing was spent.
- Real: the spawn/top-up/failsafe pipeline, SporeStack client, wallet, SSH deploy, IPv8 gossip, assurance-contract PSBT logic, Ed25519 auth.
- Not real or not integrated: semantic overlay, decentralized search, FuSST, DelftClaw, mainnet identity staking, democracy → code changes, self-hosted forge, streaming (separate branch), and any income stream.
- **Currently broken in production config:** upstream issue #31 (23 Sep 2026, from an account presenting as SporeStack's operator) says launches on SporeStack EU are disabled. `sporestack_eu` / `sporestack-eu-4gb` / `amsterdam` is the default provider. Issue #30 (7 Jul) suggests Taler and ForgeFed/Forgejo instead of BTC/GitHub. Neither issue has a reply.

## 4. History and activity

- 182 commits, 12 Jan – 5 Jul 2026 (upstream). Contributors by commits: Matei Dogariu 69 (+4 as "doga"), Stan Verlaan 60, Johan Pouwelse 35 (mostly README), Andrei Ionescu 10, Egbert Bouman 2, Aayush Shah 1, Henrique Costa 1.
- Last code commit: `c8430af`, 3 Jul 2026 09:42 (Europe/Rome). Fork's last commit: `7ca6d57` README, **4 Jul 2026 22:41 (Europe/Rome)**. Upstream's last commit: 5 Jul 2026 22:17 (Europe/Rome), README.
- Upstream: 25 stars, 3 forks, 2 open issues (#30, #31), 0 open PRs, 15 PRs merged (#1 Mycelium Jan → #29 democracy tests Jun). The repo looks dormant since early July; it appears to be an academic-semester project that ended with the theses.

## 5. Security and risks

1. **Credentials file committed in a public repository.** A credentials file is present in the public third-party (upstream) repository history. No values are reproduced here. Those credentials should be rotated. This is an upstream issue, not something introduced by the Autonomica fork.
2. **Failsafe fund capture by any peer.** On low runway, a node sweeps its **entire** BTC balance to the live peer with the highest gossiped `btc_balance_sat` (`failsafe.select_best_peer`). Peer address and balance are self-reported in IPv8 `SeedboxInfoPayload`, and I found no verification in `peer_registry`. An attacker joining the open overlay and claiming a huge balance would receive dying nodes' funds. The fallback is the operator's cold wallet.
3. **Parent knows the child's keys.** The parent generates the child's BIP39 mnemonic, SporeStack token and SSH keypair, and stores them in its own `state.db` during spawn. It retains SSH root access via the deploy key. The child therefore never has exclusive custody.
4. **Plaintext secrets at rest on rented VPSes.** The mnemonic is in `/root/data/mnemonic.txt` (0600), the token in `/root/data/sporestack_token`, and a seed is briefly in `/etc/environment` (0644 world-readable) during bootstrap. Any VPS host or provider can read everything.
5. **Remote code execution by design.** Every node `git pull`s `github.com/Tribler/superorganism-experiment` main every 60 s and restarts. Whoever controls that repo, GitHub, or a maintainer account steers the whole fleet. There's no signature or measurement check. Shell commands are built with f-strings over SSH (`set_environment_variable`, `git clone ... {repo_url}`) with light escaping. SSH host keys use `AutoAddPolicy` (TOFU) by default.
6. **Telemetry.** Optional `LOG_ENDPOINT` + `X-Api-Key` posts every decision event (balances, peers) to a central collector. Nodes also discover their public IP via an external HTTP service.
7. Hard-coded regtest RPC creds (`demo`/`superorganism`) are fine for regtest only. `pickle.load` appears in research scripts (local files only). The fork inherits all of this, and the README says itself that the code is unmaintainable.

## 6. Mapping to full sovereignty

Sovereign = no third party can read, stop, steer, or take its assets.

| Axis | Where it sits | Who can still read / stop / steer / take |
|---|---|---|
| **Privacy** | Low. Plain VPS, plaintext secrets, optional central telemetry, public gossip of IP/balance/address | VPS provider and SporeStack upstream (Vultr/DO) can read everything; parent node; log collector; any IPv8 peer sees balances |
| **Custody** | Low-to-medium. Each node has its own BIP39 wallet (good: no shared treasury). But keys are born on the parent and stored plaintext on rented hardware | Parent (holds child mnemonic + root SSH), VPS host, operator cold wallet as failsafe sink, any peer that lies in gossip |
| **Funding** | Spend-only. No income; runway = operator seed ÷ VPS cost, split 40% per spawn. Democracy pledges pay human devs, not nodes | Operator funds it; SporeStack (single payment rail + API) can refuse service, as #31 shows |
| **Continuity** | Interesting mechanics (spawn, inheritance, failsafe, write-ahead intent records, crash recovery), but it's lineage continuity, not identity continuity: a child is a new identity with a new key | Hosting expiry kills a node; GitHub repo controls upgrades; no recovery of a lost node's keys |
| **Independence from a single host/vendor** | Low. One provisioner (SporeStack, whose EU region is now disabled), one forge (GitHub), one bootstrap repo URL. IPv8 overlay itself has no DNS or central server (a genuine strength) | SporeStack, GitHub, Tribler maintainers |

**Against the five hard problems:**
1. Backdoor-free key continuity: not addressed. Keys are per-node, plaintext, and parent-generated. There is no threshold signing, TEE or recovery.
2. Identity across upgrades: the opposite. Unsigned `git pull` from a mutable branch; no measurement, reproducible build or upgrade policy. The democracy module could become the upgrade-policy layer, but it isn't wired in.
3. Halt without a backdoor: implicit and unbounded. Halts come from VPS expiry or the provider; steering comes from the GitHub repo. Both are full-power out-of-band controls.
4. Attestation without trusting chip vendors: no attestation at all.
5. Fork-free migration: replication rather than migration, by design. It deliberately forks (copies with new keys), so nothing is "moved" and nothing is provably destroyed.

**What it uniquely contributes:** an actually-running economic life cycle (buy compute with BTC → seed → reproduce → bequeath → die) on KYC-free hosting, an IPv8 DNS-free comms fabric, BTC-staked Sybil-resistant identity, and assurance-contract funding for code changes. In holon terms, it is the best existing prototype of an **agent as an organism inside a population**. It is also the closest running thing to the CNAS "self-replicating, rents its own compute" picture, so it needs careful framing on the site.

## 7. Could it be the sovereignagents.ai reference agent?

**Not as-is.** It has no LLM/agent loop, earns nothing, and is dormant. It is explicitly throw-away code owned by a university lab, and every axis has a third party who can read, stop, steer or take. It is a **strong reference for the continuity/replication and P2P layers**, and a good substrate to build on.

What a sovereign reference build would need, in order:
1. Fix the two critical issues first: rotate any committed credentials, and make failsafe recipients verifiable (signed whoami + on-chain balance proof, or only known lineage keys).
2. **Child-generated keys inside a TEE** (e.g. Enclava/dstack on SEV-SNP or TDX), sealed to the measurement; the parent sends only funds to an attested child pubkey and never holds the mnemonic or root SSH.
3. **Measured, signed upgrades**: reproducible builds, a transparency log, and an upgrade policy decided by the democracy module (or a threshold of nodes) instead of `git pull` from GitHub main. Self-hosted forge (ForgeFed/Forgejo, per #30, or git over IPv8/BitTorrent).
4. **Multi-provider provisioning**: SporeStack plus at least one other BTC/Lightning-payable host, ideally a confidential-VM provider, so no single vendor can stop the fleet.
5. **Income**: paid seeding/bandwidth, inference or search served over x402/L402/Lightning, so funding isn't a countdown.
6. Add an LLM agent loop (DelftClaw is the stated path) and encrypted, sealed memory.
7. Kill telemetry by default; peer-to-peer health via IPv8 only.

## 8. Next steps (recommended)

1. Decide the fork's purpose. Either treat it as a read-only mirror of a third-party experiment, or make it a working branch with a `SOVEREIGNTY.md` gap analysis (sections 6–7) and the two critical fixes (credential hygiene; verifiable failsafe recipients).
2. Prototype "Mycelium-in-an-enclave": one node whose wallet key is generated and sealed in a TEE, spawning a child on a second, different provider. That directly targets hard problems 1 and 5 and the vendor-independence axis.
3. Use it on the site as a case study ("closest running self-replicating agent, and every place a third party still holds power"), not as the reference agent.
