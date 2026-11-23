---
title: "Mind file (SOUL.md and constitutions)"
category: concept
status: stable
sources: []
updated: 2026-11-24
---

# Mind file

> A short document the agent loads every turn that says who it is, what it
> values and what it is trying to do. Conway's automaton writes and rewrites
> its own `SOUL.md`, alongside a protected `constitution.md` that it passes to
> every child. Together they act as genome (inherited, fixed) and
> self-concept (evolving).

## Details

- Inherited part: constitution or core rules, hash-checked so children
  cannot be given a tampered one ([conway-automaton](conway-automaton.md)).
- Evolving part: self-description, goals, lessons.
- Both should be signed and stored with the organism's memory
  ([agent-memory](agent-memory.md)).

## How it serves the organism

Keeps identity stable across model swaps: a new model reading the same mind
file behaves as the same organism.

## How it fails

Anyone who can edit it can rewrite the organism; a poisoned lesson becomes
character ([memory-poisoning](memory-poisoning.md)).

## Related

[agent-memory](agent-memory.md) · [conway-automaton](conway-automaton.md) · [self-replication](self-replication.md)

## Sources

- Conway automaton README — <https://github.com/Conway-Research/automaton>
- constitution.md — <https://github.com/Conway-Research/automaton/blob/main/constitution.md>
