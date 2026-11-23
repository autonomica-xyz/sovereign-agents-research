---
title: "Promptbreeder (2023)"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Promptbreeder

> DeepMind's Promptbreeder (Fernando et al., 2023) evolves a population of
> task prompts and also the "mutation prompts" that change them, so the way
> it improves itself also improves.

## Details

- Self-referential: mutation operators are themselves evolved.
- Beat hand-written chain-of-thought prompts on arithmetic and commonsense
  benchmarks.

## How it serves the organism

Cheapest form of self-improvement: no weight changes, only better
instructions to itself.

## How it fails

Prompt gains are task-specific and can overfit the evaluation set.

## Related

[self-improvement](self-improvement.md) · [adas](adas.md)

## Sources

- Promptbreeder, arXiv 2309.16797 — <https://arxiv.org/abs/2309.16797>
