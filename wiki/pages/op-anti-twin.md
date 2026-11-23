---
title: "Open problem: anti-twin (no forks of the organism)"
category: open-problem
status: seed
sources: [wiki/pages/open-problems.md]
updated: 2026-11-23
---

# Open problem: anti-twin

> If a host can snapshot a body and start a copy, two "selves" can spend the
> same money and sign contradictory things, and an attacker can run a twin
> to study or rob it. The organism needs exactly one live instance per
> identity, or forks that it chose, and must be able to move sealed state
> across hosts without leaving a usable copy behind.

## Details

- Building blocks: monotonic counters and rollback protection (ROTE,
  Narrator, Nimble), quorum-held leases, MPC networks that only sign for the
  currently registered instance ([anti-twin-quorum](anti-twin-quorum.md),
  [rollback-protection](rollback-protection.md)).
- NEAR Shade Agents accept many workers by design; uniqueness is enforced at
  the contract, not the body ([near-shade-agents](near-shade-agents.md)).
- dstack's zero-downtime handover moves service between instances but does
  not prove the old one is gone ([andrew-miller](andrew-miller.md)).
- Physical attacks that forge attestation can mint twins
  ([tee-fail](tee-fail.md)).

## How it serves the organism

One identity, one wallet authority, one memory line; deliberate forks only
for reproduction.

## How it fails

Strong uniqueness needs a quorum, which is itself a liveness dependency: if
the quorum is down, the organism cannot act.

## Related

[anti-twin-quorum](anti-twin-quorum.md) · [rollback-protection](rollback-protection.md) · [rehydration](rehydration.md) · [open-problems](open-problems.md)

## Sources

- ROTE, ePrint 2017/048 — <https://eprint.iacr.org/2017/048>
- Nimble (OSDI 2023) — <https://www.usenix.org/conference/osdi23/presentation/angel>
- Narrator — <https://github.com/pw0rld/narrator>
