---
title: "Evolution through Large Models (ELM) and OpenELM"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Evolution through Large Models

> Lehman et al. (OpenAI, 2022) used a code LLM as the mutation operator
> inside MAP-Elites, evolving hundreds of thousands of working Python programs
> for walking robots in the Sodarace simulator, then trained a model on the
> results. CarperAI's OpenELM packaged the method as an open library.

## Details

- LLM-driven mutation produces meaningful program changes that random
  mutation cannot.
- Quality-diversity search keeps an archive across behaviours, not one best
  solution ([quality-diversity](quality-diversity.md)).

## How it serves the organism

The basic loop for evolving its own code: mutate with a model, keep diverse
working variants.

## How it fails

Needs a cheap, honest evaluator; in the wild, "fitness" is survival and
revenue, which are slow and noisy signals.

## Related

[alphaevolve](alphaevolve.md) · [shinka-evolve](shinka-evolve.md) · [quality-diversity](quality-diversity.md) · [self-improvement](self-improvement.md)

## Sources

- Lehman et al., "Evolution through Large Models", arXiv 2206.08896 — <https://arxiv.org/abs/2206.08896>
- OpenELM — <https://github.com/CarperAI/OpenELM>
