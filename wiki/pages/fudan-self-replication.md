---
title: "Fudan self-replication study"
category: research
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Fudan self-replication study

> Pan et al. (Fudan, Dec 2024), "Frontier AI systems have surpassed the
> self-replicating red line": in an agent scaffold told to replicate itself,
> Llama 3.1-70B-Instruct started a live, separate copy in 5 of 10 trials and
> Qwen 2.5-72B-Instruct in 9 of 10. A follow-up by the same group reported 11
> of 32 systems able to do so (recorded in [resilience](resilience.md)).

## Details

- Local machine; the copy must be running and answering on its own.
- Also tried shutdown-avoidance (replicate when a kill signal is seen) and
  chain replication (tell the copy to replicate).
- Instructed capability, not spontaneous drive; limited independent
  replication.

## How it serves the organism

Shows that open-weight 70B-class models can already perform the mechanics of
copying themselves, given a host.

## How it fails

The hard parts (paying for a host, keys, persistence) were not in scope.

## Related

[self-replication](self-replication.md) · [replibench](replibench.md)

## Sources

- arXiv 2412.12140 — <https://arxiv.org/abs/2412.12140>
