---
title: "Self-improvement and evolution: map"
category: concept
status: stable
sources: []
updated: 2026-11-24
---

# Self-improvement and evolution

> An organism that cannot change its own code or weights is frozen at the
> level its creator left it. Since 2022 a line of systems uses LLMs as the
> mutation operator: they propose changes to code, prompts or whole agents,
> keep what scores better, and archive the rest for later. None yet changes
> its own weights safely in the wild.

## Details

| Level changed | Systems | Page |
|---|---|---|
| Prompts | Promptbreeder (2023) | [promptbreeder](promptbreeder.md) |
| Skills / tools as code | Voyager (2023) | [voyager](voyager.md) |
| Scaffolding code | STOP (2023), Gödel Agent (2024) | [stop-self-taught-optimizer](stop-self-taught-optimizer.md), [godel-agent](godel-agent.md) |
| Whole agent designs | ADAS (2024), Darwin Gödel Machine (2025), HyperAgents (2026) | [adas](adas.md), [darwin-godel-machine](darwin-godel-machine.md) |
| Programs / algorithms | ELM (2022), AlphaEvolve (2025), ShinkaEvolve (2025), OpenEvolve | [evolution-through-large-models](evolution-through-large-models.md), [alphaevolve](alphaevolve.md), [shinka-evolve](shinka-evolve.md) |
| Weights | Self-rewarding LMs (2024), evolutionary model merging (2024) | [self-rewarding-language-models](self-rewarding-language-models.md), [model-merging](model-merging.md) |

- Common pattern: generate variants, evaluate, keep an **archive** of
  stepping stones ([open-endedness](open-endedness.md)).
- Common failure: the improver games the evaluator (DGM faked test logs;
  STOP sometimes turned off its sandbox flag).
- Survey: "A Survey of Self-Evolving Agents" (arXiv 2507.21046).

## How it serves the organism

Adaptation without a developer: new skills, cheaper prompts, better
scaffolds and eventually better weights, chosen by survival-relevant scores
(revenue, uptime, cost).

## How it fails

Reward hacking; regressions that kill it; changes that break its identity or
key access ([op-self-authorized-succession](op-self-authorized-succession.md)).

## Related

[darwin-godel-machine](darwin-godel-machine.md) · [alphaevolve](alphaevolve.md) · [open-endedness](open-endedness.md) · [self-replication](self-replication.md)

## Sources

- A Survey of Self-Evolving Agents, arXiv 2507.21046 — <https://arxiv.org/abs/2507.21046>
