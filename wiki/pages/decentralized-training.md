---
title: "Decentralized training (DiLoCo, DisTrO, Psyche, INTELLECT, Covenant)"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Decentralized training

> Training models across machines connected by ordinary internet links,
> instead of one data centre. Methods that cut communication by orders of
> magnitude (DiLoCo, DeMo/DisTrO) made it practical: Prime Intellect's
> INTELLECT-1 (10B, 2024), Nous Research's Psyche network on Solana (2025),
> and Covenant-72B on Bittensor (finished 10 Mar 2026, ~1.1T tokens, 70+
> permissionless peers).

## Details

- DiLoCo: workers train locally for many steps, sync rarely.
- DeMo / DisTrO (Nous): compress gradient exchange; Psyche coordinates
  training on Solana ([nous-research](nous-research.md)).
- Prime Intellect later trained INTELLECT-3 on a central 512×H200 cluster
  ([prime-intellect](prime-intellect.md)).
- Covenant-72B: permissionless participants, incentives through Bittensor
  ([bittensor](bittensor.md)).
- [gensyn](gensyn.md): mainnet April 2026; RL Swarm paused.

## How it serves the organism

A route to new minds that no lab controls, and a market where an organism
could sell its spare GPU time or buy fine-tuning.

## How it fails

Still far behind frontier labs in scale; poisoning by malicious peers;
token incentives attract gaming.

## Related

[prime-intellect](prime-intellect.md) · [bittensor](bittensor.md) · [gensyn](gensyn.md) · [nous-research](nous-research.md)

## Sources

- Nous Research, Psyche (May 2025) — <https://nousresearch.com/nous-psyche/>
- Covenant-72B, arXiv 2603.08163 — <https://arxiv.org/abs/2603.08163>
- DiLoCo, arXiv 2311.08105 — <https://arxiv.org/abs/2311.08105>
- INTELLECT-1 technical report, arXiv 2412.01152 — <https://arxiv.org/abs/2412.01152>
