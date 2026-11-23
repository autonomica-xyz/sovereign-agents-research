---
title: "Self-Replicating Language Models (Hintze 2026)"
category: research
status: seed
sources: []
updated: 2026-11-23
---

# Self-Replicating Language Models

> Arend Hintze (Dalarna University / BEACON, arXiv 2611.25839, Nov 2026)
> tests three ways a language model can reproduce: emit a genome that trains
> its child, copy and mutate its own weights, or teach a child from its own
> samples. Small LMs can replicate and evolve; for a large LLM, replication by
> teaching is "technically and economically infeasible" for now.

## Details

- Selection improves children and adapts them to narrow niches.
- Selection also lowers mutation rates, and an LM can lower its own to zero,
  which may stop its evolution.
- Flagship LLMs can **write** such replicators.

## How it serves the organism

Separates "copying the weights" (cheap, no variation) from "raising a child"
(expensive, variation). An organism that wants a lineage must budget for
variation deliberately ([open-endedness](open-endedness.md)).

## How it fails

Small-model experiments; costs for large models make full reproduction a
budget question first ([earn-buy-redeploy-loop](earn-buy-redeploy-loop.md)).

## Related

[self-replication](self-replication.md) · [open-endedness](open-endedness.md) · [tierra](tierra.md)

## Sources

- arXiv 2611.25839 (Nov 2026) — <https://arxiv.org/abs/2611.25839>
