---
title: "iroh"
category: technology
status: stable
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-23
---

# iroh

> A peer-to-peer QUIC library from n0 where you **dial a public key, not an
> IP address**. It hole-punches when it can and falls back to relays that
> forward encrypted traffic. iroh 1.0 shipped on 15 Jun 2026; 1.4–1.5 followed
> by 19 Nov 2026. It is the transport under [mesh-llm](mesh-llm.md).

## Details

- Endpoint IDs are Ed25519 public keys; addresses can change without breaking
  connections.
- Official bindings: Rust, Python, Node.js, Swift, Kotlin; wire protocol stable
  across 1.x.
- Extra protocols: iroh-blobs (BLAKE3-verified transfer), iroh-gossip.
- n0 runs default public relays; anyone can run their own.

## How it serves the organism

Its bodies can find and talk to each other by key from behind NAT, with no DNS
and no fixed IP to block ([location-hiding](location-hiding.md)).

## How it fails

- Default relays and discovery are run by one company and see connection
  metadata; run your own ([op-metadata-privacy](op-metadata-privacy.md)).
- Direct connections reveal IP addresses to peers.

## Related

[mesh-llm](mesh-llm.md) · [n0-computer](n0-computer.md) · [nostr](nostr.md) · [body-stack](body-stack.md)

## Sources

- iroh 1.0 announcement (15 Jun 2026) — <https://www.iroh.computer/blog/v1>
- iroh repository — <https://github.com/n0-computer/iroh>
- Mesh LLM on the iroh blog — <https://www.iroh.computer/blog/mesh-llm>
