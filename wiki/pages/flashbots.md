---
title: "Flashbots"
category: actor
status: stable
sources: []
updated: 2026-11-23
---

# Flashbots

> Ethereum MEV research and infrastructure organisation whose TEE work
> (Flashbots X, the Teleport project) produced the first public
> agent-owned accounts (TEE_HEE, Oct 2024, with Nous Research) and ships
> reproducible TDX images used for block building.

## Details

- Teleport/Flashbots team members co-wrote "Setting Your Pet Rock Free".
- `flashbots-images` builds reproducible VM images for TDX, so others can
  check what an enclave is running ([signed-code-distribution](signed-code-distribution.md)).
- Its researchers are close to dstack ([andrew-miller](andrew-miller.md)).

## How it serves the organism

Source of practical patterns: key encumbrance, reproducible images,
TEE-hosted services that the operator cannot read.

## How it fails

Its main business is block building, not organisms; agent experiments are
side projects and can stop.

## Related

[tee-hee-he](tee-hee-he.md) · [key-encumbrance](key-encumbrance.md) · [dstack](dstack.md) · [andrew-miller](andrew-miller.md)

## Sources

- Flashbots — <https://www.flashbots.net/>
- flashbots-images — <https://github.com/flashbots/flashbots-images>
- Nous Research, "Setting Your Pet Rock Free" (Oct 2024) — <https://nousresearch.com/setting-your-pet-rock-free>
