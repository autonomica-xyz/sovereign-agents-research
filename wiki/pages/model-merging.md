---
title: "Evolutionary model merging (Sakana AI, 2024)"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Evolutionary model merging

> Sakana AI (2024) used evolutionary search to find recipes for merging
> open models' weights and layers, producing, for example, a Japanese math
> model from a Japanese chat model and English math models, without any
> gradient training.

## Details

- Merging needs only enough memory to load models, not training compute.
- Works within one architecture family.

## How it serves the organism

Cheap weight-level evolution: children can be merges of parent models with
others, a form of sexual reproduction for minds.

## How it fails

Limited to compatible models; evaluation cost; merges can lose skills.

## Related

[self-rewarding-language-models](self-rewarding-language-models.md) · [sakana-ai](sakana-ai.md) · [self-replication](self-replication.md)

## Sources

- Evolutionary Optimization of Model Merging Recipes, arXiv 2403.13187 — <https://arxiv.org/abs/2403.13187>
