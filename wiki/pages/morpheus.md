---
title: "Morpheus (MOR)"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# Morpheus

> A decentralised AI network that routes inference requests to independent
> providers and pays them through MOR staking. In 2026 it offers an
> OpenAI-compatible API with 30+ models, providers that can be tagged as
> TEE-attested (Intel TDX, AMD SEV-SNP), and a local node path that needs only
> a wallet.

## Details

- Users stake MOR to get daily inference credit rather than paying per call.
- Providers can resell capacity from others (including Venice), which may not
  be TEE-verified.
- Node software (Morpheus-Lumerin-Node) active on GitHub (Nov 2026).

## How it serves the organism

Wallet-only access to many inference providers, some attested: no account,
no card.

## How it fails

Token economics; mixed provider quality; resold capacity hides the real
backend.

## Related

[venice](venice.md) · [inference-cost-per-token](inference-cost-per-token.md) · [routstr](routstr.md)

## Sources

- Morpheus — <https://mor.org/>
- Morpheus inference API deep dive — <https://mor.org/inference-api/deep-dive>
- Morpheus-Lumerin-Node — <https://github.com/MorpheusAIs/Morpheus-Lumerin-Node>
