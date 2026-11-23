---
title: "Silent payments (BIP-352)"
category: money-rail
status: seed
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Silent payments

> One static public address that receives to a fresh, unlinkable on-chain
> output every time. The organism can publish a donation or payment address
> without showing its total balance.

## Details

- Base protocol merged into Bitcoin Core master (PR #35301, 23 Sep 2026);
  wallet send/receive support not yet in a release (Nov 2026).
- Wallets: Sparrow, Cake, Dana, BlindBit.

## How it serves the organism

Counters [public-balance-exposure](public-balance-exposure.md) for on-chain
income.

## How it fails

Scanning is heavier for the receiver; spending still links outputs unless
coins are managed carefully.

## Related

[privacy-organ](privacy-organ.md) · [public-balance-exposure](public-balance-exposure.md)

## Sources

- BIP-352 — <https://github.com/bitcoin/bips/blob/master/bip-0352.mediawiki>
- Bitcoin Core PR #35301 — <https://github.com/bitcoin/bitcoin/pull/35301>
