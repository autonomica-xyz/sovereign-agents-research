---
title: "Petals"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# Petals

> BigScience's "BitTorrent-style" system (2022) for running large models
> across volunteers' GPUs, each serving some layers. Dormant: last release
> v2.2.0 (Sep 2023), last push Sep 2024.

## Details

- Pipeline parallelism over the internet; peers found by DHT.
- Showed 100B+ models could run on consumer GPUs pooled together.

## How it serves the organism

Proof that a mind can be split across strangers' machines; ancestor of
[mesh-llm](mesh-llm.md).

## How it fails

Peers see activations (and can infer prompts); dormant project; slow.

## Related

[mesh-llm](mesh-llm.md) · [exo](exo.md) · [distributed-llama](distributed-llama.md)

## Sources

- Petals releases — <https://github.com/bigscience-workshop/petals/releases>
