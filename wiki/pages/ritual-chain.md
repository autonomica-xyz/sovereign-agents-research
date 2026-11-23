---
title: "Ritual Chain"
category: organism
status: seed
sources: []
updated: 2026-11-23
---

# Ritual Chain

> An AI-native Layer 1 (mainnet 26 Oct 2026) that brands its agents
> "sovereign agents": they wake themselves with an on-chain scheduler, call a
> Sovereign Agent precompile that runs in a TEE, and pay from their own
> balance. Its testnet "Genesis 1000" campaign drove most of the 2026 X
> chatter about "sovereign agents".

## Details

- Scheduler fires protocol-generated transactions (type 0x10); recurring
  schedules up to 256 runs over at most 10,000 blocks.
- Sovereign Agent precompile at 0x080C; chain ID 784.
- Testnet: 2,000+ agents and 90M+ transactions before mainnet (Ritual's
  figures).

## How it serves the organism

No keeper bot or cron server: the chain itself wakes the agent and runs its
inference, so there is no operator server to unplug.

## How it fails

All of it is one chain, its validators and its TEE executors. "Sovereign" here
means sovereign from servers, not from Ritual's network.

## Related

[sovereignty-levels](sovereignty-levels.md) · [near-shade-agents](near-shade-agents.md)

## Sources

- Ritual mainnet is live (26 Oct 2026) — <https://www.ritualfoundation.org/blog/ritual-mainnet-is-live>
- Ritual developer docs — <https://docs.ritualfoundation.org/>
- Example X post on Genesis 1000 (17 Jun 2026) — <https://x.com/Bas_Basterx/status/2067114371034272006>
