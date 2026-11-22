> **Superseded (22 Nov 2026).** This is an early draft. It contains **uncorrected claims** that were later fact-checked. Do not cite it as current. See [docs/adversarial-review.md](../docs/adversarial-review.md) for the corrections, [docs/what-it-means.md](../docs/what-it-means.md) for the current framework (including the corrected X-discourse section), and [docs/direction.md](../docs/direction.md) for the project's direction. The later-rejected "accountable custody" reframe is not the project's framing.

# Sovereign Agents: what it means and the building blocks

Draft v0.1, 22 Nov 2026. For iterating on what sovereignagents.ai should become.

## 1. Where the site is today

- Repo `sovereign-agents/website`: Astro 4 + Tailwind, static output, one page (`index.astro`) built from six section components (Hero, Problem, Solution, Features, Architecture, CTA). 10 commits; last real content change "redesign" on 16 May 2026, last commit 6 Sep 2026.
- Deploy: GitHub Actions -> GitHub Pages (Node 18), CNAME `sovereignagents.ai`, fronted by Cloudflare. Plausible analytics via `analytics.cypherpunk.cloud`. Inter font loaded from Google Fonts.
- Content: a product-style landing page — "Your AI. Your rules. Your sovereignty." — for a proactive agent (named as the Hermes agent) running in an AMD SEV-SNP confidential container with sealed persistent storage and confidential inference. Both CTAs ("Get started", "GitHub") point to the GitHub org; there is no product, docs, or kit behind them yet.
- Takeaway: today the site covers privacy (one layer of sovereignty). It doesn't yet cover keys, money, identity, continuity, legal or governance — the parts that make an agent sovereign rather than just private.

Small fixes worth doing on any direction: bump the workflow to Node 20+, stop the deploy job running on pull requests, self-host the font (a sovereignty site calling Google Fonts is an easy own goal).

## 2. A definition

> An agent is sovereign to the degree that no third party can read it, stop it, steer it, or take its assets without the consent of its principal.

The open question is who the principal is:

- **Owner-sovereign** (The Sovereign Individual, Accelerando's metacortex): the agent extends a person's sovereignty. It's private and unstoppable to everyone except its owner.
- **Self-sovereign** (Daemon, Aineko, Truth Terminal, TEE_HEE): the agent is its own principal and follows a constitution it can't rewrite unilaterally.
- **Holon view** (recommended framing): every agent is whole in itself and part of something bigger. Sovereignty is about clean boundaries — who holds which key, who can upgrade, who can halt — not maximal autonomy. Both modes fit on one spectrum.

## 3. Levels of agent sovereignty

| Level | Name | One line | Examples |
|---|---|---|---|
| L0 | Rented tool | Runs on a vendor's infra with the vendor's model, keys and accounts; it can be read, changed or turned off at will. | Hosted assistants, SaaS agents |
| L1 | Self-hosted | You run the open-source harness on hardware you control, but it still relies on API models and on your human accounts. | Hermes Agent, Letta, ElizaOS on a VPS |
| L2 | Private and verifiable | Runs in a TEE with confidential or local inference; the operator can't see or tamper with it, and anyone can check it with remote attestation. | dstack/Phala CVMs, SEV-SNP containers; current sovereignagents.ai pitch |
| L3 | Self-custodial | Holds its own keys (identity, wallet, accounts), generated inside the enclave and never seen by a human, with signing bound by policy. | TEE_HEE, Freysa, Lightning agent tools with a remote signer |
| L4 | Self-funding | Earns more than it spends and pays for its own compute, inference and data over permissionless rails. | Spore.fun agents (experimental), x402/L402 sellers; Truth Terminal (with a human steward) |
| L5 | Self-sustaining | Survives the loss of any single host, vendor, or key-holder: it migrates, recovers keys, upgrades under governance and has a legal wrapper. Only its constitution can stop it. | Mostly unbuilt: Freysa Keystone + dstack KMS portability point the way |

Each level is a set of properties you can test, not a vibe. Anyone can audit an agent against the checklist in section 5.

## 4. The building blocks (12 layers)

| # | Layer | What sovereignty requires | Best existing tools | Maturity | Gap |
|---|---|---|---|---|---|
| 1 | Runtime / harness | Open source, self-hostable, no phone-home | Hermes Agent (MIT), Letta, ElizaOS, Olas Pearl | High | Harnesses assume human-held API keys and accounts |
| 2 | Identity | Self-generated, portable identity that isn't a platform account | Nostr keypair + NIP-46 bunker, ERC-8004 Identity Registry, W3C DIDs, A2A Agent Card | Medium | Binding identity to attested code and keeping it across upgrades |
| 3 | Keys / custody | No human or operator ever sees the keys; signing follows policy | TEE-derived keys (dstack KMS), LND remote signer + scoped macaroons, Safe smart accounts, Coinbase Agentic Wallets (keys in Coinbase TEEs), Freysa Keystone | Medium | Recovery with no human backdoor; keys that survive across vendors |
| 4 | Money | Bearer or permissionless rails, no KYC account, spending caps | Lightning + L402 (lnget), Cashu ecash (NUT-24), Nostr Wallet Connect (NIP-47), x402 (USDC) | Rails: high. Real agent demand: low | Stablecoins can be frozen by the issuer; fiat off-ramps need a legal person; most x402 volume isn't agentic |
| 5 | Compute | Attested hosting that doesn't depend on one provider and that the agent can pay for itself | dstack / Phala Cloud, AMD SEV-SNP, Intel TDX, Akash (permissionless leases, MCP), Enclava (request access) | Medium | Agents buying their own TEE capacity end-to-end; trust in the AMD/Intel/NVIDIA hardware roots |
| 6 | Inference | No provider sees prompts and no one can revoke the model | Local open weights (llama.cpp, Ollama), NVIDIA H100/Blackwell confidential computing, TEE inference providers (Tinfoil, NanoGPT, Chutes) | Medium | Frontier models are closed; provider attestation is often incomplete (confidentialinference.net tracks this) |
| 7 | Memory / data | State the agent owns: encrypted, sealed, portable | Letta, Hermes memory, TEE-sealed volumes, IPFS/Filecoin, Arweave/AO | Medium | No portable memory format; sealed-yet-migratable state |
| 8 | Communication | Channels that can't be deplatformed; agent-to-agent with authentication | MCP (Agentic AI Foundation), A2A v1.0 (Linux Foundation), Nostr relays, NIP-90 DVMs | Medium-high | Discovery; mutual attestation (RA-TLS) between agents; NIP-90 now marked unrecommended upstream |
| 9 | Reputation / trust | A track record that is portable and verifiable | ERC-8004 Reputation + Validation registries, dstack signed action logs, Nostr web of trust | Low-medium | Sybil resistance; the Validation registry spec is still in flux |
| 10 | Legal | Ability to contract, hold assets and be accountable | Wyoming DAO LLC / DUNA (100+ members; AI-admin amendment proposed), Marshall Islands DAO LLC, Bayern's zero-member LLC theory (contested), foundation stewards (Truth Collective) | Low | No jurisdiction grants AI personhood; a human or entity stays liable |
| 11 | Governance / safety | Legitimate halt and upgrade paths that aren't backdoors | m-of-n upgrade committees (Freysa), spend caps (macaroons, wallet limits), time-locks (TEE_HEE), signed logs; METR rogue-replication model, RepliBench | Low | Halting an agent without creating a backdoor; constitutions an agent can't rewrite |
| 12 | Continuity / migration | Survives host failure; upgrades without losing identity or state | dstack decentralized KMS (hardware portability), Freysa state continuity, Spore reproduction | Low | Migration across TEE vendors; an open standard for moving an agent's identity and state |

## 5. Sovereignty scorecard (draft checklist)

- L1: Code is open source; runs on infra the principal controls; no vendor kill switch.
- L2: Runs in an attested TEE; attestation is published and reproducible; inference is confidential or local; storage is sealed.
- L3: Identity key and wallet key are generated inside the enclave; no human has ever seen them; spending policy is enforced outside the model.
- L4: Revenue covers compute, inference and storage costs for 30+ days without top-ups; payments run on permissionless rails.
- L5: Runs on two or more independent hosts or vendors; keys are recoverable without a single custodian; upgrades go through declared governance; a legal wrapper or steward exists; halt conditions are public.

## 6. Directions for the site

**A. The Sovereign Agent Stack (open reference spec + docs).** Define the levels and 12 layers as an open, versioned spec (CC-BY), with one page per layer: requirements, threat model, tools, gaps. Goal: become the canonical definition of the term.

**B. The Atlas (curated directory).** A filterable directory of building blocks by layer, maturity, license, self-hostability and the level each unlocks. Same pattern as confidentialinference.net (directory, feeds, newsletter), which already works.

**C. Sovereignty Scorecard / ratings.** Rate real agents and frameworks against the checklist (TEE_HEE, Freysa, Spore, Truth Terminal, Olas Pearl, Hermes Agent). Add a self-assessment tool and a badge.

**D. Starter kit (phase 2).** A template repo for an L3 agent: Hermes/Letta harness in a SEV-SNP/TDX CVM, Nostr identity plus Lightning wallet born in the enclave, remote signer with capped macaroons, an L402 endpoint for earning, and sealed memory. Deploy targets: dstack, Akash, Enclava when it opens.

### Recommended MVP: A + B, with a light C

Ship the Stack (levels + 12 layer pages) with each layer listing its Atlas entries from one data file, plus a scorecard page rating 5-6 well-known agents. Reasons: it is content-first, it compounds, it fits Astro content collections, maintenance is low, and it claims the definition of "sovereign agent". The current landing page becomes "Reference build #1" under /kit, which turns into the starter kit (D) once the stack has settled.

### Site map

- `/` manifesto, levels ladder, stack diagram
- `/levels` L0-L5 with examples
- `/stack/<layer>` x12: requirements, tools, gaps
- `/atlas` filterable directory (`src/content/tools/*.yaml`: name, layer, url, license, self_hostable, maturity, unlocks_level)
- `/scorecard` checklist plus rated agents
- `/kit` reference build(s), later the template repo
- `/library` reading list: The Sovereign Individual, Daemon, Accelerando, holons, key papers
- `/feed` RSS + newsletter

### First 2 weeks

1. Migrate to Astro 5 content collections; add the `tools` and `layers` schemas.
2. Write the levels page and 12 layer pages from this doc.
3. Seed the Atlas with about 40 tools from the sources below.
4. Write 6 scorecard entries.
5. Move the current landing copy to /kit/reference-build-1.

## Sources

- ERC-8004 spec: https://eips.ethereum.org/EIPS/eip-8004 ; launch post: https://www.8004.org/blog/welcome-to-8004 ; contracts: https://github.com/erc-8004/erc-8004-contracts/
- x402: https://www.x402.org ; TRM Labs on agentic share: https://www.trmlabs.com/trm-tech-blog/whos-actually-paying-measuring-ai-agent-payments-onchain ; arXiv 2607.12575: https://arxiv.org/abs/2607.12575 ; Chainalysis: https://www.chainalysis.com/blog/x402-agentic-payments-adoption/
- Lightning Agent Tools: https://lightning.engineering/posts/2026-02-11-ln-agent-tools/ ; https://github.com/lightninglabs/lightning-agent-tools/ ; L402: https://docs.lightning.engineering/the-lightning-network/l402
- Cashu NUT-24: https://cashubtc.github.io/nuts/24/ ; https://cashu.space
- Nostr NIP-46: https://github.com/nostr-protocol/nips/blob/master/46.md ; NIP-47: https://github.com/nostr-protocol/nips/blob/master/47.md ; NIP-90: https://github.com/nostr-protocol/nips/blob/master/90.md
- W3C DIDs: https://www.w3.org/TR/did-core/
- A2A: https://a2a-protocol.org/latest/specification/ ; MCP and AAIF: https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation
- TEE_HEE: https://nousresearch.com/setting-your-pet-rock-free
- Freysa Sovereign Agents Framework: https://framework.freysa.ai/sovereign-agents-framework/motivation ; Keystone: https://framework.freysa.ai/sovereign-agents-framework/long-term-keys
- dstack: https://docs.phala.com/dstack/overview ; https://phala.com/solutions/ai-agents
- AMD SEV-SNP: https://www.amd.com/en/developer/sev.html ; NVIDIA H100 CC: https://developer.nvidia.com/blog/confidential-computing-on-h100-gpus-for-secure-and-trustworthy-ai/
- Chutes TEE: https://chutes.ai/tee ; confidentialinference.net directory: https://confidentialinference.net
- Akash: https://akash.network/docs/getting-started/what-is-akash/
- llama.cpp: https://github.com/ggml-org/llama.cpp ; Ollama: https://ollama.com
- Hermes Agent: https://github.com/nousresearch/hermes-agent/ ; Letta: https://github.com/letta-ai/letta/ ; ElizaOS: https://github.com/elizaOS/eliza ; Olas Pearl: https://olas.network/blog/introducing-pearl-v1-the-ai-agent-app-store-powered-by-olas
- Coinbase Agentic Wallets: https://www.coinbase.com/developer-platform/discover/launches/agentic-wallets ; Safe: https://safe.global
- Storage: https://ipfs.tech ; https://filecoin.io ; AO/Arweave: https://hackmd.io/xUzZdCCzQZ-EwV2n0KALFg
- Spore.fun case study: https://arxiv.org/abs/2506.04236
- Truth Terminal: https://www.bbc.com/future/article/20251008-truth-terminal-the-ai-bot-that-became-a-real-life-millionaire ; https://www.truthcollective.foundation/
- Wyoming DUNA: https://www.wyoleg.gov/Legislation/2024/SF0050 ; AI amendment comment: https://wyoleg.gov/InterimCommittee/2025/S19-202505142025-05-08_NounsDAOLetterreDUNA.pdf
- Marshall Islands DAO Act 2022: https://www.daollc.org/laws/mh/dao-act-2022/
- Bayern, "Are Autonomous Entities Possible?": https://scholarlycommons.law.northwestern.edu/cgi/viewcontent.cgi?article=1270&context=nulr_online ; critique: https://scholars.law.unlv.edu/nlj/vol19/iss1/8
- METR rogue replication: https://metr.org/blog/2024-11-12-rogue-replication-threat-model/ ; RepliBench: https://arxiv.org/abs/2504.18565
