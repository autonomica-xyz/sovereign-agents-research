---
title: "distributed-llama"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# distributed-llama

> A C++ project (b4rtaz) that splits LLM inference across several devices
> over Ethernet with tensor parallelism, aimed at clusters of cheap boards and
> old PCs. v0.17.0 (7 Nov 2026) added Qwen3.5 support; about 3.1K stars.

## Details

- Root node plus workers; quantized weights; scales with device count up to
  network limits.

## How it serves the organism

Turns a handful of scavenged machines into one usable mind.

## How it fails

LAN only; all devices must be trusted.

## Related

[exo](exo.md) · [llama-cpp](llama-cpp.md) · [iot-substrate](iot-substrate.md)

## Sources

- distributed-llama repository — <https://github.com/b4rtaz/distributed-llama>
- v0.17.0 release — <https://github.com/b4rtaz/distributed-llama/releases/tag/v0.17.0>
