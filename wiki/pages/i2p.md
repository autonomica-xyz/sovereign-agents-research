---
title: "I2P (Invisible Internet Project)"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# I2P

> An anonymous overlay network (since 2003) using "garlic routing": every
> participant routes traffic for others, and services ("eepsites") are
> addressed by a hash of their public key. Implementations: Java I2P and
> i2pd (C++). SporeStack's API was reachable over I2P.

## Details

- Designed for hidden services inside the network, unlike Tor, which is
  mostly used to reach the normal web.
- Unidirectional tunnels; each peer is also a router.

## How it serves the organism

A second hidden-service network for diversity with Tor: an address that
reveals no IP and is owned by key.

## How it fails

Smaller network, so easier to observe; slow; joining makes the host a router,
which is visible to its provider.

## Related

[tor-onion-services](tor-onion-services.md) · [lokinet](lokinet.md) · [nym](nym.md) · [location-hiding](location-hiding.md)

## Sources

- I2P — <https://geti2p.net/en/>
- i2pd — <https://i2pd.website/>
