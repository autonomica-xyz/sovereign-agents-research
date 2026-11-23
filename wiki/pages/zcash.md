---
title: "Zcash"
category: money-rail
status: stable
sources: []
updated: 2026-11-24
---

# Zcash

> Proof-of-work coin (launched Oct 2016) with zero-knowledge shielded pools
> that hide sender, receiver and amount. About 29.0% of supply (roughly 4.94M
> ZEC) sat in shielded pools on 23 Nov 2026; the rest is transparent, which
> weakens the anonymity set compared with [monero](monero.md), where all
> outputs are private by default.

## Details

- Pools: Sprout (legacy), Sapling, Orchard, and the new Ironwood pool.
- Shielded-to-shielded transfers reveal only that a transaction happened.
- Moving between transparent and shielded pools leaks timing and amounts.

## How it serves the organism

Strong cryptographic privacy for its treasury if it stays fully shielded
([public-balance-exposure](public-balance-exposure.md)).

## How it fails

Delistings on custodial exchanges; shield/deshield links; smaller liquidity
than BTC or stablecoins.

## Related

[monero](monero.md) · [privacy-organ](privacy-organ.md) · [coinjoin](coinjoin.md)

## Sources

- ZecStats, shielded percentage (23 Nov 2026) — <https://zecstats.org/shielded-percentage>
- Zcash protocol specification — <https://zips.z.cash/protocol/protocol.pdf>
