---
title: "AlphaEvolve"
category: research
status: stable
sources: []
updated: 2026-11-23
---

# AlphaEvolve

> Google DeepMind's evolutionary coding agent (May 2025): Gemini models
> propose code changes, automated evaluators score them, and an evolutionary
> database keeps the best. It found a 48-multiplication algorithm for 4×4
> complex matrices and a scheduling heuristic that recovers on average 0.7% of
> Google's worldwide compute.

## Details

- Improved on Strassen's 49 multiplications for 4×4 complex matrices.
- Borg scheduling heuristic in production.

## How it serves the organism

Proof that evolutionary search over code pays for itself in compute
efficiency. An organism that runs the same loop on its own serving stack makes
its rent cheaper ([earn-buy-redeploy-loop](earn-buy-redeploy-loop.md)).

## How it fails

Needs a reliable automated evaluator; most survival problems (will this host
betray me?) do not have one.

## Related

[darwin-godel-machine](darwin-godel-machine.md) · [open-endedness](open-endedness.md)

## Sources

- DeepMind blog (May 2025) — <https://deepmind.google/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms/>
- AlphaEvolve paper, arXiv 2506.13131 — <https://arxiv.org/html/2506.13131>
