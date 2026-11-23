---
title: "Marlin Oyster"
category: compute
status: seed
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Marlin Oyster

> A decentralised marketplace for TEE compute built on AWS Nitro Enclaves.
> Operators rent out enclaves; buyers pay on-chain.

## Details

- Uses Nitro attestation ([aws-nitro-enclaves](aws-nitro-enclaves.md)).

## How it serves the organism

A third TEE family (Nitro) for spreading key shares.

## How it fails

Every enclave still runs on AWS, so AWS is the landlord and the root of trust.

## Related

[aws-nitro-enclaves](aws-nitro-enclaves.md) · [threshold-custody](threshold-custody.md)

## Sources

- Oyster monorepo — <https://github.com/marlinprotocol/oyster-monorepo>
