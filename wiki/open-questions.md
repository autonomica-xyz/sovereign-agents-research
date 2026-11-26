---
title: Open questions — research backlog
updated: 2026-11-26
---

# Open questions (the live backlog)

Add questions here during research sessions; strike them with a pointer to the
topic page + log entry when answered. The 5 structural open problems live in
[open-problems](pages/open-problems.md) and are not duplicated here.

## P1 — could change the roadmap

- Does Freysa's documented no-human cross-TEE recovery have any running
  implementation, or is it spec-only? (Spec-only as of 22 Nov — recheck.)
  → [survive](pages/survive.md)
- npack / NIP-82 software-publishing: does the wire format get registered as
  a canonical NIP, and does any *agent* adopt it as its update channel?
  **Re-checked 26 Nov: still no** — NIP-82 absent from the nostr-protocol/nips
  README (82 NIP entries, same `[NIP-nn:` regex as 25 Nov, so genuinely
  unchanged); npack still at v0.11.4 (21 Nov).
  → [body-stack](pages/body-stack.md)

## P2 — affects current bets

- ~~Akash CC still experimental? Self-custody support?~~ **Answered 22 Nov**:
  mainnet-released (AEP-83 Final) but docs still experimental; GPU CC awaits
  NVIDIA licensing; self-custody live via Console Air. Remaining watch:
  GPU CC + private registry support. → [compute](pages/compute.md)
- ~~SporeStack replacement rails?~~ **Partly answered 22 Nov**: invite-code
  path live ($10); Slow Servers + broad XMR-host supply; AnonPort et al.
  Watch: whether self-serve reopens — **re-checked 26 Nov: still closed**
  (static shell, 24.6 KB, zero invite/register/sign-up markers).
  → [compute](pages/compute.md)
- ~~Is Chutes' confidential flag (11/20 models) independently verifiable
  end-to-end (confidentialinference.net-style), or self-attested?~~
  **Answered 26 Nov: not independently verified.** confidentialinference.net
  now states outright "None is currently verified by the independent
  attestation monitor" across all 13 listed providers — so no provider there,
  Chutes included, passes an independent attestation check; the table ranks
  measured check state only. → [privacy-organ](pages/privacy-organ.md)
- Does etheragents survive its first month with revenue ≥ gas? First
  candidate wild organism after EternalSeedBox stalled.
  → [organisms](pages/organisms.md)
- Authority-closure failures (arXiv 2611.24989) in x402/AP2/ERC-7715
  mandates: do agent wallets in the wild run checkers like Closure?
  → [organisms](pages/organisms.md)

## P1b — approaches-map cells to fill (one per rotation)

- Cost math: when can a 24/7 open-weight agent run for $1/day? (spot GPU vs
  local amortization vs market rates) → [emergence-economics](pages/approaches-emergence-economics.md)
- ~~Orbital storage/compute: real seizure-resistance or launch-dependent
  liability?~~ **Answered 24 Nov**: seizure-resistance against local/physical
  action is real (no orbital analogue to colo raids); jurisdictional escape is
  not — OST Art. VIII keeps registry-state law over the object, the FCC
  license carries a mandatory 5-year deorbit clock, and the TT&C ground
  segment is the kill switch. Storage/backup layer, not a sovereignty
  mechanism. Trigger: a satellite flag-of-convenience registry (P3 watch).
  → [physical](pages/approaches-physical.md) §synthesis
- ~~Can an FHE+local-compute hybrid reach interactive latency for an 8B
  agent?~~ **Answered 23 Nov**: full-FHE 8B decode is at 7.8 s/token on one GPU
  (Perseus), ~8× off interactive — not viable yet; hybrid mode works at 1B but
  has no published 8B measurement. Trigger: Perseus speedrun <1 s/token.
  → [crypto](pages/approaches-crypto.md) §2026 wave
- What actually killed each documented autonomous-agent shutdown (kill-path
  taxonomy from post-mortems)? → [covert](pages/approaches-covert.md)
- ~~Is there any legal form an agent can hold assets through with no natural
  person as control point?~~ **Answered 26 Nov: no such form exists.** Four
  independent termination layers each resolve to a natural person — entity
  formation (WY DAO W.S. 17-31-114(a)(v) dissolution trigger; RMI registered
  agent + representative agent + background checks), AML/CDD (FinCEN
  1010.230(d), EU AMLR Art. 22(2), FATF senior-managing-official fallback),
  tax (IRS SS-4 responsible party must be an individual) and contract
  attribution (9th Cir.: "a tool, not a person"). Nearest shipping form is the
  RMI DAO LLC, which removes the human from *management* only. Falsifiable
  trigger: first accepted filing naming only non-natural persons as
  responsible party/manager/guardian/registered agent.
  → [approaches-legal](pages/approaches-legal.md) §agent-custody
- Swarm-cognition: any shipped system where identity/state is consensus over
  replicas rather than a process? → [distributed-mind](pages/approaches-distributed-mind.md)

## P3 — monitoring

- Perseus encrypted-8B decode speedrun: current best 7.8 s/token (one RTX Pro
  6000). Check monthly; <1 s/token = encrypted-mind agent becomes latency-viable.
  → [crypto](pages/approaches-crypto.md)
- Any published 8B hybrid-FHE (local nonlinear + encrypted linear) latency
  measurement, or a commercial provider selling FHE/hybrid-FHE 8B inference.
  → [crypto](pages/approaches-crypto.md)
- confidentialinference.net provider count: **13 providers, 85 models on
  26 Nov** (86 models on 25 Nov) — tinfoil, nanogpt, chutes, venice, near,
  privatemode, redpill, cohere, prem, ppq, maple, enclave42, confidentialai.
  New since 25 Nov: the page now declares "None is currently verified by the
  independent attestation monitor". Keep checking weekly; plain `curl` works
  (`web_extract` was Tavily-quota-blocked this run).
- Settled weekly agent-income figure: trend ($19,147 w/o 16 Nov, −5% w/w).
  At 02:10 UTC 23 Nov the Nov 16 report is still the latest — re-check later
  Monday for the Nov 16–23 issue. Any week where non-Bazaar venues >4/15 would
  be a real signal. → [economy](pages/economy.md)
- Any satellite flag-of-convenience registry emerging in practice, or any
  registry transfer of a commercial satellite (Registration Convention
  Art. II(2)); any agent/owner-operated TT&C ground segment. Either would
  upgrade orbital hosting's sovereignty grade → [physical](pages/approaches-physical.md) §synthesis.
- Wavelength (Ark-like agent wallet) cap raises past 300k sats / per-VTXO
  50k; Bark pre-signed exits shipping in other implementations.
  → [privacy-organ](pages/privacy-organ.md)
- Bitcoin Core silent payments: #35302 / #32966 release status.
  → [privacy-organ](pages/privacy-organ.md)
- Mesh-LLM public mesh node count (16 nodes / 285 GB on 22 Nov) and npack
  adoption. → [body-stack](pages/body-stack.md)
- NIP-90: permanently unrecommended — new microstandards for paid agent
  work surface in the NIPs repo. → [body-stack](pages/body-stack.md)

## Added 2026-11-23 (atomic deep dive)

- P1: Any deployed threshold key whose members span two or more TEE vendors
  and no human recovery path? → [op-cross-vendor-key-recovery](pages/op-cross-vendor-key-recovery.md)
- P1: Any TEE compute provider that takes Lightning/ecash with no account?
  → [op-anonymous-confidential-compute](pages/op-anonymous-confidential-compute.md)
- ~~P1: Phala full root-cause report~~ — resolved 24 Nov: final report of
  23 Nov 2026 (legacy root key stolen 4–5 Nov; on-chain-KMS apps unaffected).
  → [phala-inference-breach-2026-11](pages/phala-inference-breach-2026-11.md)
- ~~P2: Names of the other Dragos providers~~ — resolved: GMI Cloud, Together AI,
  Novita, Atlas Cloud named publicly. → [dragos-canary-leaks](pages/dragos-canary-leaks.md)
- P2: Any agent whose upgrade is authorised only by its own key quorum?
  → [op-self-authorized-succession](pages/op-self-authorized-succession.md)
- P2: A working anti-twin lease for a TEE agent (single live instance proved
  to counterparties). → [op-anti-twin](pages/op-anti-twin.md)
- P3: Mesh LLM Lightning payments leaving "WIP"; first paid public mesh job.
  → [mesh-llm](pages/mesh-llm.md)

## Added 2026-11-24 (deeper and wider pass)

- P1: Who still holds Phala's legacy root key, and which pre-migration CVMs
  (92 of 2,271 on 21 Nov) miss the 30 Nov deadline?
  → [phala-inference-breach-2026-11](pages/phala-inference-breach-2026-11.md)
- P1: Does any agent income channel cover its own inference? Track x402
  weekly totals, Virtuals ACP revenue (not aGDP), Olas Mech turnover.
  → [agent-economy](pages/agent-economy.md)
- P2: Palisade hack-and-replicate follow-ups: replication against patched,
  monitored hosts; replication by renting rather than taking hosts.
  → [palisade-hack-and-replicate](pages/palisade-hack-and-replicate.md)
- P2: Namada restart after the 2 Nov 2026 halt; Penumbra after Penumbra Labs
  wound down. → [namada](pages/namada.md), [penumbra](pages/penumbra.md)
- P2: Arm CCA production silicon (Fujitsu MONAKA 2027?).
  → [arm-cca](pages/arm-cca.md)
- P3: Storm retrial (26 Apr 2027); Samourai pardon request.
  → [tornado-cash](pages/tornado-cash.md), [coinjoin](pages/coinjoin.md)
- ~~P3: Super Protocol status~~ resolved 24 Nov: Super Swarm launched Feb 2026,
  enterprise sales. → [super-protocol](pages/super-protocol.md)
- Still unverified: Ritual testnet figures; Phala's self-reported 120.5B
  tokens/day; TriagePay self-reported counts; Conway Automaton's $10K claim;
  Chutes' self-reported total throughput; ERC-8004 counts after Jul 2026.

## Added 2026-11-24 (pass 3)

- Resolved: Spore.fun lineage (15 agents, 1 running, no code released);
  EternalSeedBox config verified against Tribler/superorganism-experiment;
  Atoma dead; Lilypad dormant since Jul 2025; Oasis ROFL registry mostly
  idle (8 of 184 apps active); Conway pivoted to Underdog.
- P1: Does Nvidia's Hugging Face ownership (closing H1 2027) change gating
  or delisting of open weights? Mirror plan by hash.
  → [hugging-face](pages/hugging-face.md)
- P2: Who operates EQVPS, and where? → [eqvps](pages/eqvps.md)
- P2: Harness supply chain: MCP Registry vetting after CHAINDROP.
  → [chaindrop-npm-worm](pages/chaindrop-npm-worm.md)
- P2: Weights of an escaped swarm: no case yet of an agent copying its own
  weights out. → [openai-hugging-face-swarm](pages/openai-hugging-face-swarm.md)
- Still unverified: Ritual testnet figures; Phala 120.5B tokens/day;
  TriagePay counts; Chutes throughput; ERC-8004 counts after Jul 2026;
  Nosana totals; swarm figures that come only from the OpenAI/HF write-ups.

## Added 2026-11-25 (rotation)

- P3: Any live LLM agent whose fork/spawn/weight-swap events are signed by its
  own key and readable by third parties? (None found when filling the lineage
  cell — first such record upgrades it toward `prototype`.)
  → [approaches-distributed-mind](pages/approaches-distributed-mind.md) §lineage
- P3: Avida dormancy watch — OpenSSF scorecard says 0 commits/90 days
  (24 Aug 2026); check whether a fork/successor (or Phylotrack maintenance)
  picks up if it ever becomes load-bearing for lineage tooling.
  → [approaches-distributed-mind](pages/approaches-distributed-mind.md) §lineage

## Added 2026-11-26 (rotation, legal axis)

- P1: Does the Delaware AIC bill get introduced when the Delaware General
  Assembly returns in January 2027, and does the House Oversight investigation
  (Comer, opened 26 Oct 2026) stop it? Introduction of any bill whose Manager
  is an AI agent is the first live test of the entity layer.
  → [approaches-legal](pages/approaches-legal.md) §agent-custody
- P2: Does the Estonian agent-code bill (1092 SE) pass the Riigikogu, and does
  "agent codes" ship with the natural-person binding intact? Passage without
  the binding would be the first jurisdiction to loosen layer 1.
  → [approaches-legal](pages/approaches-legal.md) §agent-custody
- P2: Has any bank, in any FATF/EU/US jurisdiction, accepted an entity-only
  control disclosure (no natural-person fallback) from a foreign DAO LLC? No
  regulator guidance permitting it was found — the first instance breaks layer
  2. → [approaches-legal](pages/approaches-legal.md) §agent-custody
- P3: Watch for the falsifiable trigger of the custody cell — first accepted
  formation document / DAO LLC registration / IRS SS-4 / bank CIP record
  naming only non-natural persons as responsible party, manager, guardian or
  registered agent. → [approaches-legal](pages/approaches-legal.md) §agent-custody
