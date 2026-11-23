---
title: "Rehydration (restoring the organism on a new body)"
category: concept
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Rehydration

> Rehydration is booting the organism on a fresh host and restoring its state
> and keys, so the death of any one machine is not the death of the organism.
> Storage is production-grade; rollback-safe, attestation-gated rehydration is
> still prototype.

## Details

- **State stores:** [arweave-ao](arweave-ao.md) keeps process state and its full
  message log permanently, restorable on another node; [walrus-seal](walrus-seal.md)
  keeps ciphertext on Walrus with policy-gated key servers;
  [blossom](blossom.md) stores content-addressed blobs on many servers.
- **Keys:** released by a quorum after attestation
  ([attestation-gated-key-release](attestation-gated-key-release.md)).
- **Freshness:** a counter that cannot be rewound ([rollback-protection](rollback-protection.md)).
- **Cross-vendor migration** has no live path; same-vendor only (Intel MigTD,
  SEV-SNP SVSM). The practical route is redeploy plus key restore.
- dstack v0.6.6 (20 Nov 2026) added key-epoch crossing and a
  `dstack-key-recovery` tool for pre-rotation epochs.

## How it serves the organism

It is how the organism survives host death, supplier shutdown and seizure.

## How it fails

- If restore depends on one KMS operator, that operator holds the organism's
  life.
- Old snapshots restored by an attacker create a twin
  ([anti-twin-quorum](anti-twin-quorum.md)).

## Related

[survive](survive.md) · [attestation-gated-key-release](attestation-gated-key-release.md) · [op-cross-vendor-key-recovery](op-cross-vendor-key-recovery.md)

## Sources

- [docs/state-of-the-art.md §Drive 1](../../docs/state-of-the-art.md).
- AO-Core / HyperBEAM — <https://hyperbeam.arweave.net/build/introduction/what-is-ao-core.html>
- dstack v0.6.6 release (20 Nov 2026) — <https://github.com/Dstack-TEE/dstack/releases/tag/v0.6.6>
- Intel MigTD — <https://github.com/intel/MigTD>
