---
title: "Self-Rewarding Language Models (2024)"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Self-Rewarding Language Models

> Yuan et al. (Meta, 2024) had Llama 2 70B judge its own answers and train on
> its own preferences (iterative DPO). After three iterations it outperformed
> several proprietary models of the time on AlpacaEval 2.0, with no human
> preference labels in the loop.

## Details

- The model improves both as a responder and as a judge.
- Risk: drifting toward what it likes rather than what is true.

## How it serves the organism

A path to improving its own weights with no outside labeller, if it has the
compute to fine-tune.

## How it fails

Self-judgement drift; needs GPU time an organism may not afford.

## Related

[model-merging](model-merging.md) · [self-improvement](self-improvement.md)

## Sources

- Self-Rewarding Language Models, arXiv 2401.10020 — <https://arxiv.org/abs/2401.10020>
