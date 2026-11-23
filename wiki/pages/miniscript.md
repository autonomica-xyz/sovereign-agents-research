---
title: "Miniscript"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# Miniscript

> A structured subset of Bitcoin Script (Wuille, Poelstra, Towns) that makes
> spending policies composable and analysable: "2 of these 3 keys, or this
> key after 6 months". Watch-only support landed in Bitcoin Core 25 (2023)
> and wallets like Liana build time-locked recovery on it.

## How it serves the organism

Lets it hold bitcoin under policies like "my key shares, or after N blocks
of silence, my successor's key", without new consensus rules
([op-self-authorized-succession](op-self-authorized-succession.md)).

## How it fails

Policies are visible when spent; time locks need someone to keep refreshing
coins.

## Related

[bitcoin](bitcoin.md) · [bitcoin-vaults](bitcoin-vaults.md) · [frost](frost.md)

## Sources

- Miniscript reference — <https://bitcoin.sipa.be/miniscript/>
- Bitcoin Optech, miniscript — <https://bitcoinops.org/en/topics/miniscript/>
- Liana wallet — <https://wizardsardine.com/liana/>
