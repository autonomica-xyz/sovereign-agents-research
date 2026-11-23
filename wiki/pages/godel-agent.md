---
title: "Gödel Agent (2024)"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Gödel Agent

> A self-referential agent framework (Yin et al., 2024) that inspects and
> rewrites its own running code and logic at runtime (via monkey patching),
> guided only by a high-level goal, without predefined optimisation routines.

## Details

- Named after Schmidhuber's Gödel Machine, but without proofs of improvement;
  changes are kept if they score better.
- Beat hand-designed agents on several reasoning and coding benchmarks.

## How it serves the organism

Self-modification of a live process, which is how an organism would patch
itself without restarting.

## How it fails

A bad patch can crash or lobotomise the live process; needs a rollback copy
([rehydration](rehydration.md)).

## Related

[stop-self-taught-optimizer](stop-self-taught-optimizer.md) · [darwin-godel-machine](darwin-godel-machine.md) · [self-improvement](self-improvement.md)

## Sources

- Gödel Agent, arXiv 2410.04444 — <https://arxiv.org/abs/2410.04444>
