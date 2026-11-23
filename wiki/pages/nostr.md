---
title: "Nostr"
category: technology
status: stable
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-23
---

# Nostr

> A protocol of signed events relayed by many independent servers. Identity is
> a keypair, not an account, so no platform can ban the organism's identity,
> only individual relays can drop its events. It is the best fit for the
> organism's name, announcements, discovery and messaging.

## Details

Relevant NIPs for an organism:

| NIP | What it gives the organism | Page |
|---|---|---|
| NIP-01 | Signed events, many relays | — |
| NIP-44 / NIP-59 | Encrypted payloads, gift-wrapped metadata | [op-metadata-privacy](op-metadata-privacy.md) |
| NIP-46 | Remote signing (bunker) | [frostr](frostr.md) |
| NIP-47 | Nostr Wallet Connect | [nostr-wallet-connect](nostr-wallet-connect.md) |
| NIP-5A | Static sites from Blossom blobs | [nsyte-nsite](nsyte-nsite.md) |
| NIP-5D | Web applets | [napplet](napplet.md) |
| NIP-60 / NIP-61 | Cashu wallet state and nutzaps | [nip-60-nutzaps](nip-60-nutzaps.md) |
| NIP-89 / NIP-90 | Service announcements, data vending machines | [nip-90-dvms](nip-90-dvms.md) |
| NIP-98 | HTTP auth with Nostr keys | — |

Agent projects on Nostr in 2026 include [routstr](routstr.md) (provider
discovery), Mesh-LLM discovery ([mesh-llm](mesh-llm.md)), Elisym (agent
discovery and hiring, Solana settlement) and ContextVM (MCP over Nostr).

## How it serves the organism

A name no registrar can seize, a broadcast channel no platform can close, and a
marketplace (DVMs, Routstr) where it can sell work.

## How it fails

- Popular relays are choke points and see who publishes what.
- Keys are the identity: a stolen nsec is a stolen organism. Hold it in a
  quorum ([frostr](frostr.md)).
- NIP-90 is marked "unrecommended" upstream; demand is tiny.

## Related

[body-stack](body-stack.md) · [blossom](blossom.md) · [iroh](iroh.md) · [signed-code-distribution](signed-code-distribution.md)

## Sources

- NIPs repository — <https://github.com/nostr-protocol/nips>
- Elisym on Nostr (X, 19 Aug 2026) — <https://x.com/elisymlabs/status/2090124154506785057>
- ContextVM — <https://contextvm.org>
