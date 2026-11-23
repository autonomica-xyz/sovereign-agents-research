---
title: "io.net"
category: compute
status: seed
sources: [docs/research-notes.md]
updated: 2026-11-24
---

# io.net

> A decentralised GPU marketplace (Solana). Confidential compute is offered
> **on request** for H100, H200 and B200, using TDX or SEV-SNP with NVIDIA GPU
> protection and signed inference responses.

## Details

- Earlier research notes (Nov 2026) recorded no self-serve TEE; the docs now
  describe a confidential-compute and confidential-inference offering that is
  requested rather than self-serve.
- Last full third-party report found (Blockworks Intel, Q1 2025): $5.7M quarterly revenue (+82.6% QoQ),
  about 6,720 average daily verified GPUs (−11.1%). No comparable verified figures for
  2026 were found.

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
- Blockworks Intel, State of io.net Q1 2025 — <https://app.blockworks.com/report/state-of-io-net-q1-2025>
