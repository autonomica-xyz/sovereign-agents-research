---
title: "Roadmap: L0–L5 and the five axes"
status: stable
sources: [docs/direction.md, docs/what-it-means.md]
updated: 2026-11-22
---

# Roadmap: L0–L5 across five axes

L5 (self-sustaining) is the goal. Each level is a set of testable properties
(see [scorecard](scorecard.md)), not a vibe.

| Level | Name | What it means |
|---|---|---|
| L0 | Rented tool | Vendor infra, model, keys, accounts. Vendor can read, change or kill it. |
| L1 | Self-hosted | Open harness on hardware you control; still depends on API models and human accounts. |
| L2 | Private and verifiable | TEE, confidential or local inference, remote attestation. |
| L3 | Self-custodial | Keys born in the enclave, never seen by a human; policy-enforced signing. |
| L4 | Self-funding | Earns more than it spends; pays its own compute over permissionless rails. |
| L5 | Self-sustaining (goal) | Survives losing any host, vendor or key-holder; migrates without cloning; recovers keys with no human quorum; upgrades by trustless succession; can replicate. |

Examples per level are in [what-it-means.md](../../docs/what-it-means.md).
The current sovereignagents.ai site sits at L2; most open problems are L3–L5
([engineering agenda](engineering-agenda.md)).

## The five axes

An agent advances on each independently; L5 = maximum on all five.

| Axis | L5 target |
|---|---|
| Privacy | No host, vendor or operator can read its memory, prompts or state |
| Custody | It alone holds its keys; recovery needs no human quorum |
| Funding | Earns and pays over censorship-resistant rails (Bitcoin, Lightning, Cashu) |
| Continuity | Persists through host failure, trustless succession, migration without cloning, replication |
| Independence | No single host, chip vendor, model provider or jurisdiction is a point of control |

