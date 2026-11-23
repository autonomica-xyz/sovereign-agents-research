---
title: "Sovereignty levels L0–L5"
category: concept
status: stable
sources: [docs/what-it-means.md]
updated: 2026-11-23
---

# Sovereignty levels L0–L5

> A ladder from "a bot an operator runs" (L0) to "a digital organism that is
> its own principal" (L5). Each step removes one party who could read, stop,
> steer or seize the agent. L5 is the goal.

## Details

| Level | Who can stop or read it | Example (Nov 2026) |
|---|---|---|
| L0 | The operator, fully | Most hosted agents |
| L1 | Operator, but the agent has its own wallet | [virtuals-protocol](virtuals-protocol.md) agents, [truth-terminal](truth-terminal.md) (human signs) |
| L2 | The host cannot read keys (TEE), developer still upgrades | [tee-hee-he](tee-hee-he.md), [near-shade-agents](near-shade-agents.md) |
| L3 | Keys in a quorum, upgrades gated by a timelock or policy | [dstack](dstack.md) apps with on-chain KMS, [ritual-chain](ritual-chain.md) agents |
| L4 | Runs on several vendors and markets, pays its own rent, buys hosts itself | Not observed end-to-end |
| L5 | Nobody can read, stop, steer or seize it; it picks its own successor and reproduces | Not observed |

The five axes scored at each level are privacy, custody, funding, continuity
and independence ([roadmap](roadmap.md), [scorecard](scorecard.md)).

## How it serves the organism

It turns a vague word ("sovereign") into a checklist of removable choke points.

## How it fails

Marketing uses "sovereign agent" for L1 systems. Ritual's 2026 testnet
campaign called any deployed agent "sovereign" even though the chain's
scheduler and precompiles are a single network ([ritual-chain](ritual-chain.md)).
Score the architecture, not the label.

## Related

[digital-organism](digital-organism.md) · [roadmap](roadmap.md) · [infrastructural-sovereignty](infrastructural-sovereignty.md)

## Sources

- [docs/what-it-means.md](../../docs/what-it-means.md) — level definitions.
- Ritual mainnet announcement (26 Oct 2026) — <https://www.ritualfoundation.org/blog/ritual-mainnet-is-live>
