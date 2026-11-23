---
title: "Ark (Arkade, Bark, Wavelength)"
category: money-rail
status: seed
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Ark

> An off-chain Bitcoin layer where users hold virtual UTXOs (VTXOs) issued by
> an operator, with a pre-signed path to exit on-chain without the operator's
> help. Self-custodial in principle, but VTXOs must be refreshed periodically.

## Details

- Arkade live Oct 2025; Second's **Bark** on mainnet Jun 2026, v0.8.1
  (5 Nov 2026) added pre-signed emergency-exit CPFP and reproducible builds.
- Lightning Labs' **Wavelength** (23 Oct 2026) is Ark-like and agent-oriented
  ([lightning](lightning.md)).
- Standards work tracked by Bitcoin Optech (V-PACK, hArk).

## How it serves the organism

Cheap payments while keeping a unilateral exit: an operator can stop serving
but cannot take the coins.

## How it fails

The organism must stay online to refresh VTXOs before expiry; missing a refresh
during a long outage risks funds. Operators see payment flows.

## Related

[lightning](lightning.md) · [privacy-organ](privacy-organ.md) · [custodian-seizure](custodian-seizure.md)

## Sources

- Bark changelog — <https://second.tech/docs/changelog>
- Arkade trust model — <https://docs.arkadeos.com/learn/concepts/security-and-trust-model>
- Optech Ark topic — <https://bitcoinops.org/en/topics/ark>
