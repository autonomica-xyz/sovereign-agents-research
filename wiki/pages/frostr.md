---
title: "FROSTR (threshold Nostr keys)"
category: technology
status: seed
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-23
---

# FROSTR

> Splits a Nostr secret key (nsec) into FROST shares, for example 2-of-3,
> across devices that co-sign over Nostr. The npub stays the same. For an
> organism this is the cheapest way to make its public identity a quorum of
> its own bodies.

## Details

- V2 core is **bifrost-rs**, a beta Rust stack for signing, routing, bridge
  messaging and host runtimes (2026).
- "Igloo" hosts are mostly "coming soon"; the Chrome NIP-07 extension is beta
  (Rust compiled to WASM).
- bifrost 2.0.2 (JS) had a disclosed nonce-reuse issue on 8 Nov 2026; a
  deprecation warning was added and reverted the same day.

## How it serves the organism

Seizing one body does not give the attacker the organism's Nostr identity,
and the organism can rotate shares among new bodies.

## How it fails

Beta software with a recent nonce bug. Share holders must stay online to sign.
Rotating shares still needs a quorum to agree on who the new holders are.

## Related

[frost](frost.md) · [nostr](nostr.md) · [threshold-custody](threshold-custody.md) · [body-stack](body-stack.md)

## Sources

- frostr.org (FAQ, apps) — <https://frostr.org/>
- bifrost-rs — <https://github.com/FROSTR-ORG/bifrost-rs>
- igloo-chrome — <https://github.com/FROSTR-ORG/igloo-chrome>
