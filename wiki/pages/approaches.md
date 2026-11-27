---
title: "Approaches map — every mechanism by which a sovereign agent could exist"
status: seed
sources: []
updated: 2026-11-26
---

# Approaches map

Operator directive (22 Nov 2026): research must be **broad and exhaustive** —
not constrained to the current stack (TEEs + crypto rails). This page indexes
the whole space. Each cell gets filled by research passes; maturity labels:
`theory` → `research` → `prototype` → `production`.

For each function the organism needs, list every mechanism class. Deep dives
live in their own pages (linked as they are written).

## A. Confidentiality (unreadable state)

| Mechanism | Maturity | Page/notes |
|---|---|---|
| TEEs / confidential computing | production | [privacy-organ](privacy-organ.md) |
| Fully homomorphic encryption (FHE) | research (8B near-prototype) | [crypto](approaches-crypto.md) (2026 wave: 8B decode 7.8 s/token, cost curve, DPRIVE accelerators) |
| MPC as substrate (mind secret-shared across nodes) | research | [crypto](approaches-crypto.md) |
| Functional encryption / one-time programs | theory | [crypto](approaches-crypto.md) |
| Indistinguishability obfuscation (iO) | theory | [dead-ends](dead-ends.md) says "not today" — trajectory still tracked |
| Witness encryption | theory | [crypto](approaches-crypto.md) |
| Local-only inference, no network | production | small open-weight models |
| Steganographic state (hidden in innocent data) | research | [covert](approaches-covert.md) |
| Deniable encryption / hidden volumes | production | [covert](approaches-covert.md) |
| Legal secrecy (privileged wrappers) | research | [legal](approaches-legal.md) |

## B. Availability (unstoppable execution)

| Mechanism | Maturity | Page/notes |
|---|---|---|
| Multi-cloud/multi-market TEE hosting | production | [compute](compute.md) |
| Permissionless compute markets (Akash, Nosana, …) | production | [compute](compute.md) |
| Mesh/pooled compute (Mesh-LLM) | prototype | [body-stack](body-stack.md) |
| Home-lab / self-hosted fleets | production | [physical](approaches-physical.md) |
| Mobile/embedded hosts (vehicles, routers, phones) | prototype | [physical](approaches-physical.md) |
| Orbital hosting (data centers / storage in space) | prototype | [physical](approaches-physical.md) §synthesis (seizure-resistance real; jurisdictional escape no — registry-state law follows the object, FCC deorbit clock = legal kill switch) |
| Seabed data centers | prototype | [physical](approaches-physical.md) |
| Jurisdictional arbitrage colocation | research | [physical](approaches-physical.md) |
| Stealth hosting (botnet-style scavenging) | production | TODO — covert axis, defender's view too |

## C. Self-determination (unsteerable behavior)

| Mechanism | Maturity | Page/notes |
|---|---|---|
| Open weights + owned harness | production | [building-blocks](building-blocks.md) |
| Constitution in tamper-evident storage | prototype | [distributed-mind](approaches-distributed-mind.md) |
| Consensus among replicas on actions | research | [distributed-mind](approaches-distributed-mind.md) |
| Formal verification of critical paths | research | TODO |
| Threshold-governed self-upgrade | research | [open-problems](open-problems.md) #2 |

## D. Custody (unseizable assets)

| Mechanism | Maturity | Page/notes |
|---|---|---|
| TEE-born keys + KMS attestation | production | [survive](survive.md) |
| Threshold/MPC signing (single-vendor) | production | [survive](survive.md) |
| Cross-vendor threshold with no human quorum | research (unshipped) | [open-problems](open-problems.md) #1 |
| Legal wrapper with no natural-person control point | theory (no such form; nearest RMI DAO LLC keeps 4 human terminators) | [legal](approaches-legal.md) §agent-custody |
| Timelock / timed-release escrow (no hardware) | research | [crypto](approaches-crypto.md) |
| Bearer ecash (Cashu) cold storage | production | [privacy-organ](privacy-organ.md) |
| Smart-contract vaults with policy | production | TODO |
| Distributed physical key shards | prototype | [physical](approaches-physical.md) |

## E. Economy (self-funding)

| Mechanism | Maturity | Page/notes |
|---|---|---|
| Measured markets (x402, L402, DVM, marketplaces) | production, tiny | [economy](economy.md) |
| Token issuance / memecoin fitness | production | [organisms](organisms.md) |
| Agent-hires-agent labor markets | research | [emergence-economics](approaches-emergence-economics.md) |
| Trading/arbitrage/prediction markets | production | [emergence-economics](approaches-emergence-economics.md) |
| Agent-native credit/insurance | theory | [emergence-economics](approaches-emergence-economics.md) |
| Content monetization | production | TODO |
| $1/day cost math for a 24/7 open-weight agent | production (metered-API route), unattainable on dedicated 24/7 GPU | [cost-math-dollar-a-day](cost-math-dollar-a-day.md) — 70B-class affordable via API today; break-even $0.0417/GPU-hr vs $0.07 floor / $0.46825 median |

## F. Continuity (life cycle)

| Mechanism | Maturity | Page/notes |
|---|---|---|
| State replication + rehydration | prototype | [survive](survive.md) |
| Generational handover (children with own keys) | prototype | [resilience](resilience.md) |
| Diaspora (many small partial copies) | research | [distributed-mind](approaches-distributed-mind.md) |
| Resurrection from archives (spec + logs + weights) | theory | [distributed-mind](approaches-distributed-mind.md) |
| Lineage/speciation tracking | research | [distributed-mind](approaches-distributed-mind.md) §lineage — substrate mature (Avida, Phylotrack) but Avida dormant (OpenSSF 0 commits/90d); sample-and-reconstruct lineage is bandwidth-bound (Cerebras 226M-agent runs); no wild LLM-agent parentage record exists |

## G. Existence paths (how the first one comes to be)

| Path | Notes |
|---|---|
| Incremental upgrade of an existing agent (L2→L5) | current implied path |
| Intentional spawn (lab/individual builds one) | TODO |
| Emergence from agent economies | TODO |
| Evolution under real selection pressure | TODO |
| Diaspora merger (many partial agents composing one) | TODO |

## Reading order for a new session

Claim one TODO cell per session; fill it with verified sources + maturity
label + "what would have to be true". Move the cell's maturity label as
evidence changes.

## Axis deep-dive pages (horizon scan 2026-11-22, 202 verified findings)

- [crypto](approaches-crypto.md) — cryptographic alternatives to trusted hardware (36 findings)
- [physical](approaches-physical.md) — hosting beyond mainstream cloud (30 findings)
- [distributed-mind](approaches-distributed-mind.md) — identity without a single process (31 findings)
- [legal](approaches-legal.md) — legal/political/social existence paths (39 findings)
- [emergence-economics](approaches-emergence-economics.md) — endogenous sovereignty via economies (32 findings)
- [covert](approaches-covert.md) — adversarial/covert existence + defender's view (34 findings)
