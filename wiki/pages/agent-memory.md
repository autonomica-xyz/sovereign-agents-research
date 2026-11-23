---
title: "Agent memory and identity continuity"
category: concept
status: stable
sources: []
updated: 2026-11-24
---

# Agent memory and identity continuity

> An organism's identity is its keys plus its memory. Keys prove who it is;
> memory makes it the same mind across restarts, moves and upgrades. Memory
> systems range from a single self-written identity file (Conway's
> `SOUL.md`) to tiered virtual context (MemGPT/Letta), memory streams with
> reflection (Generative Agents) and linked notes (A-MEM).

## Details

- **Identity file:** a short, self-authored description loaded every turn
  ([mind-file](mind-file.md)).
- **Working vs archival memory:** [memgpt-letta](memgpt-letta.md) pages
  memory in and out of the context window like an OS.
- **Reflection:** Generative Agents (Park et al., 2023) summarise memories
  into higher-level beliefs.
- **Linked notes:** A-MEM (2025) builds a Zettelkasten-like graph.
- **Snapshots:** whole-state checkpoints let a body be restored elsewhere
  ([agent-snapshots](agent-snapshots.md), [rehydration](rehydration.md)).
- **Continuity rules:** memory must be encrypted at rest under keys only the
  organism holds, signed so tampering is visible, and protected from
  rollback ([rollback-protection](rollback-protection.md)) and poisoning
  ([memory-poisoning](memory-poisoning.md)).

## How it serves the organism

Without memory it is a new agent every boot; with portable, sealed memory it
survives host loss.

## How it fails

Memory leaks reveal plans; poisoned memory steers it; lost memory is death
even if keys survive.

## Related

[memgpt-letta](memgpt-letta.md) · [mind-file](mind-file.md) · [agent-snapshots](agent-snapshots.md) · [memory-poisoning](memory-poisoning.md)

## Sources

- Generative Agents, arXiv 2304.03442 — <https://arxiv.org/abs/2304.03442>
- A-MEM, arXiv 2502.12110 — <https://arxiv.org/abs/2502.12110>
- MemGPT, arXiv 2310.08560 — <https://arxiv.org/abs/2310.08560>
