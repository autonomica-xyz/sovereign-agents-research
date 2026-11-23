---
title: "io.net"
category: compute
status: seed
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# io.net

> A decentralised GPU marketplace (Solana). Confidential compute is offered
> **on request** for H100, H200 and B200, using TDX or SEV-SNP with NVIDIA GPU
> protection and signed inference responses.

## Details

- Earlier research notes (Nov 2026) recorded no self-serve TEE; the docs now
  describe a confidential-compute and confidential-inference offering that is
  requested rather than self-serve.

## How it serves the organism

A large GPU pool when it needs bulk compute for training or batch work.

## How it fails

"On request" means a sales process, not permissionless purchase; account
required.

## Related

[nosana](nosana.md) · [akash](akash.md) · [nvidia-confidential-computing](nvidia-confidential-computing.md)

## Sources

- io.net confidential compute — <https://io.net/docs/guides/clouds/confidential-compute-overview>
- io.net confidential inference — <https://io.net/docs/guides/confidential-inference/overview>
