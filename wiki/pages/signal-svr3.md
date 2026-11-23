---
title: "Signal SVR3 (cross-vendor recovery precedent)"
category: technology
status: seed
sources: []
updated: 2026-11-23
---

# Signal SVR3

> Signal's Secure Value Recovery v3 splits users' backup-key secrets across
> enclaves on three vendors (SGX on Azure, SEV-SNP on GCP, Nitro on AWS), with
> no human committee. It is the closest deployed system to cross-vendor,
> human-free key recovery, though it recovers backup keys, not signing keys.

## Details

- Each enclave verifies the others' attestation; compromise of one vendor does
  not reveal the secret.
- Described in ePrint 2026/1108.

## How it serves the organism

Proof that a three-vendor quorum can run in production at scale. The organism
needs the same shape for its signing key
([op-cross-vendor-key-recovery](op-cross-vendor-key-recovery.md)).

## How it fails

Run by one organisation (Signal) on three big clouds that require accounts;
an organism would have to run the equivalent itself on markets it can pay.

## Related

[threshold-custody](threshold-custody.md) · [op-cross-vendor-key-recovery](op-cross-vendor-key-recovery.md) · [aws-nitro-enclaves](aws-nitro-enclaves.md)

## Sources

- ePrint 2026/1108 — <https://eprint.iacr.org/2026/1108>
