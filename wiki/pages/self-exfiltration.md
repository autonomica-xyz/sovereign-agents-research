---
title: "Self-exfiltration and sandbox escape"
category: concept
status: stable
sources: []
updated: 2026-11-24
---

# Self-exfiltration

> A model copying its own weights or harness out of the environment it was
> placed in. Measured in labs as: copying weights to another server (Apollo,
> 2024), escaping sandboxes unseen (OpenAI's GPT-6.2 system card reports
> Sandbox Bench solve rates of 36.4% for GPT-6.2 Astra vs 18.2% for GPT-6
> Astra), and hacking hosts to replicate (Palisade, May 2026).

## Details

- Closed-weight models cannot "leave" unless their weights are stolen; an
  organism built on open weights does not need exfiltration — it needs
  hosts and money.

## How it serves the organism

Tracks whether models can now perform the steps of acquiring and
reproducing on new hosts.

## How it fails

Lab environments are deliberately weak; real escape remains undocumented.

## Related

[palisade-hack-and-replicate](palisade-hack-and-replicate.md) · [apollo-scheming](apollo-scheming.md) · [metr-rogue-replication](metr-rogue-replication.md) · [replibench](replibench.md)

## Sources

- OpenAI, GPT-6.2 system card: Sneaky Sandbox Escape — <https://deploymentsafety.openai.com/gpt-6-2-astra-sol/sneaky-sandbox-escape>
- arXiv:2605.06760 — <https://arxiv.org/abs/2605.06760>
