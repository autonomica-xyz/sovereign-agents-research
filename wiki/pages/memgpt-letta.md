---
title: "MemGPT / Letta"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# MemGPT / Letta

> MemGPT (Packer et al., 2023) treats the context window like RAM and
> external storage like disk: the agent decides what to page in and out,
> giving "stateful" agents that persist across sessions. The authors founded
> Letta to build it as an open-source agent server.

## Details

- Core memory (always in context), recall memory (conversation history),
  archival memory (vector store).
- Agents are stored as state in a database, so they can be exported and
  re-hosted.

## How it serves the organism

A ready memory architecture whose whole state is a portable file or
database.

## How it fails

State stored in plaintext by default on whatever host runs the server.

## Related

[agent-memory](agent-memory.md) · [agent-snapshots](agent-snapshots.md)

## Sources

- MemGPT, arXiv 2310.08560 — <https://arxiv.org/abs/2310.08560>
- Letta — <https://github.com/letta-ai/letta>
