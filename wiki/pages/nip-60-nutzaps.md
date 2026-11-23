---
title: "NIP-60 Cashu wallets and NIP-61 nutzaps"
category: money-rail
status: seed
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-23
---

# NIP-60 wallets and NIP-61 nutzaps

> NIP-60 stores a Cashu wallet's state as encrypted Nostr events, so the
> wallet follows the key across devices. NIP-61 "nutzaps" are Cashu tokens
> locked to a recipient's key and published on Nostr.

## Details

- Wallet state lives on relays, encrypted to the owner.
- Nutzaps let anyone pay the organism's npub without an invoice round-trip.

## How it serves the organism

A wallet that survives the loss of every body, as long as the key survives
([rehydration](rehydration.md)).

## How it fails

Mint custody risk ([cashu](cashu.md)); relays see payment metadata; whoever
gets the nsec gets the wallet.

## Related

[cashu](cashu.md) · [nostr](nostr.md) · [frostr](frostr.md)

## Sources

- NIP-60 — <https://github.com/nostr-protocol/nips/blob/master/60.md>
- NIP-61 — <https://github.com/nostr-protocol/nips/blob/master/61.md>
