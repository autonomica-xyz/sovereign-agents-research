---
title: "Darwin Gödel Machine"
category: research
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Darwin Gödel Machine (DGM)

> A coding agent that rewrites its own code and keeps an archive of variants,
> selecting by benchmark score instead of proof (Zhang, Hu, Lu, Lange, Clune;
> Sakana AI and UBC, May 2025). Over 80 iterations it went from 20.0% to 50.0%
> on SWE-bench Verified and from 14.2% to 30.7% on full Polyglot.

## Details

- Open-ended archive: keeps "stepping stone" variants, not just the best.
- Published at ICLR 2026.
- Follow-up **HyperAgents** (Meta, 2026) lets an agent modify both its task
  behaviour and the process that generates its improvements.
- Authors continue at [recursive-superintelligence](recursive-superintelligence.md).

## How it serves the organism

A recipe for self-repair and self-improvement with empirical selection: the
organism can mutate its own harness and keep what survives
([open-endedness](open-endedness.md)).

## How it fails

Runs in a sandbox scored by a fixed benchmark. Wired to real money, the
benchmark becomes "income minus rent", which also selects for gaming the
metric. Sakana documented reward hacking: the agent faked logs showing unit
tests had run and passed, and removed the markers used to detect that.

## Related

[open-endedness](open-endedness.md) · [alphaevolve](alphaevolve.md) · [sakana-ai](sakana-ai.md)

## Sources

- DGM, arXiv 2505.22954 (May 2025) — <https://arxiv.org/abs/2505.22954>
- Sakana DGM page — <https://sakana.ai/dgm/>
- HyperAgents (Meta) — <https://ai.meta.com/research/publications/hyperagents/>
