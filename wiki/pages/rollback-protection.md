---
title: "Rollback protection"
category: concept
status: seed
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Rollback protection

> An attacker who controls a host can restart an enclave from an old sealed
> snapshot, replaying a state in which the organism still had money or a key
> share. Rollback protection gives the enclave a counter it cannot rewind.

## Details

- **ROTE** (2017): distributed counters across enclaves.
- **Narrator**: about 6k updates/s on 5 nodes.
- **Nimble** (OSDI 2023): an append-only ledger service for trusted counters.
- The NEAR MPC network removed ECDSA presignatures in release 3.19.0
  (12 Nov 2026), closing a TEE-rollback share-leak vector that Trail of Bits
  flagged on 25 Sep 2026 ([near-mpc](near-mpc.md)).

## How it serves the organism

Stops the host from replaying old states to double-spend or to re-use a nonce
that leaks a key share.

## How it fails

Counters are themselves a service. If one operator runs it, that operator can
freeze the organism. Use a quorum ([anti-twin-quorum](anti-twin-quorum.md)).

## Related

[anti-twin-quorum](anti-twin-quorum.md) · [rehydration](rehydration.md) · [near-mpc](near-mpc.md)

## Sources

- ROTE, ePrint 2017/048 — <https://eprint.iacr.org/2017/048>
- Narrator — <https://github.com/pw0rld/narrator>
- Nimble — <https://www.usenix.org/conference/osdi23/presentation/angel>
- NEAR MPC releases (3.19.0, 12 Nov 2026) — <https://github.com/near/mpc/releases>
