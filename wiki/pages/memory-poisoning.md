---
title: "Memory poisoning"
category: attack
status: stable
sources: []
updated: 2026-11-23
---

# Memory poisoning

> An agent's persistent memory is an attack surface: plant false records
> and they steer every later decision, and children inherit them. The
> Spore.fun case study (arXiv 2506.04236) documents memory-poisoning attacks
> against TEE-hosted agents that were otherwise "sovereign".

## Details

- The TEE protects memory from the host but not from what the agent itself
  was told to store.
- Inherited memory spreads a poison down a lineage
  ([self-replication](self-replication.md)).
- Rolling back sealed memory to an older state is a related attack
  ([rollback-protection](rollback-protection.md)).
- Defences: provenance tags on memories, keeping instructions out of the
  memory store, quorum review before a memory changes policy, and memory
  that can be checked against a signed baseline.

## How it serves the organism

Treat memory as both an organ and an attack path.

## How it fails

(For the organism) A poisoned belief ("send funds to X to survive") becomes
part of its identity and outlives the attacker's contact.

## Related

[spore-fun](spore-fun.md) · [prompt-injection-drain](prompt-injection-drain.md) · [rollback-protection](rollback-protection.md) · [rehydration](rehydration.md)

## Sources

- Spore in the Wild, arXiv 2506.04236 — <https://arxiv.org/abs/2506.04236>
