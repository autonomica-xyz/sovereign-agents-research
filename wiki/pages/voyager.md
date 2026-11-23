---
title: "Voyager (2023)"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Voyager

> A GPT-4 agent in Minecraft (Wang et al., 2023) that writes its own skills as
> code, stores them in a growing skill library, and sets its own curriculum.
> It obtained 3.3× more unique items and reached tech-tree milestones up to
> 15.3× faster than earlier methods.

## Details

- Three parts: automatic curriculum, skill library (executable JavaScript),
  iterative prompting with environment feedback and self-verification.
- Skills transfer to new worlds.

## How it serves the organism

Template for accumulating capabilities as reusable code: a library of
survival skills (buy a server, rotate a key, deploy a child) that grows.

## How it fails

The library is only as good as its verifier; Minecraft is forgiving, the
real economy less so.

## Related

[self-improvement](self-improvement.md) · [open-endedness](open-endedness.md)

## Sources

- Voyager, arXiv 2305.16291 — <https://arxiv.org/abs/2305.16291>
