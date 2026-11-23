---
title: "Quality-diversity and MAP-Elites"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Quality-diversity

> Search methods that keep many different good solutions instead of one
> best. MAP-Elites (Mouret and Clune, 2015) divides a space of behaviours
> into cells and keeps the best solution found in each. LLM-driven systems
> (ELM, AlphaEvolve, ShinkaEvolve) reuse this archive idea.

## How it serves the organism

A population of differently specialised offspring survives shocks that kill
any single design ([resilience](resilience.md)).

## How it fails

Needs a good behaviour descriptor and lots of evaluation compute.

## Related

[novelty-search](novelty-search.md) · [evolution-through-large-models](evolution-through-large-models.md) · [open-endedness](open-endedness.md) · [alphaevolve](alphaevolve.md)

## Sources

- Mouret & Clune, "Illuminating search spaces by mapping elites" — <https://arxiv.org/abs/1504.04909>
