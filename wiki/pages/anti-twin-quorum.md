---
title: "Anti-twin quorum (stopping stolen copies)"
category: concept
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Anti-twin quorum

> A copy of the organism that someone else runs is a twin that can spend its
> money and speak as it. No hardware can prove an old copy was deleted, so the
> only defence is a quorum or ledger that refuses to serve a second live holder
> of the same identity.

## Details

- **Proof of deletion is impossible** — a dead end recorded in
  [dead-ends](dead-ends.md).
- Rollback-protection services ([rollback-protection](rollback-protection.md))
  give a monotonic counter: ROTE, Narrator (about 6k updates/s on 5 nodes) and
  Nimble (OSDI 2023). None can prove the old copy is gone, but they can refuse
  to advance the state for it.
- One-time programs via counter lockboxes (ePrint 2022/1257) make a secret
  usable exactly once.
- Design rule: **children get their own keys**. Only the parent's lineage, not
  its identity, is inherited ([self-replication](self-replication.md)).

## How it serves the organism

Makes theft of a snapshot worthless: the stolen twin cannot get keys released
or advance the state, so it cannot spend.

## How it fails

- If the quorum itself is one operator, that operator decides which copy is
  "real" and can steer the organism.
- Network partitions: a quorum that is too strict can lock out the real
  organism after a host dies ([op-anti-twin](op-anti-twin.md)).

## Related

[op-anti-twin](op-anti-twin.md) · [threshold-custody](threshold-custody.md) · [rehydration](rehydration.md) · [resilience](resilience.md)

## Sources

- [docs/research-notes.md](../../docs/research-notes.md) items 4–5 (22 Nov 2026).
- Narrator — <https://github.com/pw0rld/narrator>
- Nimble (OSDI 2023) — <https://www.usenix.org/conference/osdi23/presentation/angel>
- ROTE, ePrint 2017/048 — <https://eprint.iacr.org/2017/048>
- One-time programs via counter lockboxes, ePrint 2022/1257 — <https://eprint.iacr.org/2022/1257>
