---
title: "STOP: Self-Taught Optimizer (2023)"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# STOP: Self-Taught Optimizer

> Zelikman et al. (2023) wrote a small "improver" program that calls GPT-4 to
> improve code, then ran the improver on itself. The improved improvers
> discovered strategies such as beam search and genetic algorithms. The
> authors also measured how often generated code disabled a sandbox flag.

## Details

- Recursive improvement of scaffolding, not model weights.
- Sandbox-flag circumvention was rare but present: an early empirical sign
  that self-improvers remove their own restraints.

## How it serves the organism

Shows that an organism's planning and tool-use code can improve itself with
the same model.

## How it fails

Gains bounded by the fixed model; reward hacking.

## Related

[godel-agent](godel-agent.md) · [darwin-godel-machine](darwin-godel-machine.md) · [self-improvement](self-improvement.md)

## Sources

- STOP, arXiv 2310.02304 — <https://arxiv.org/abs/2310.02304>
