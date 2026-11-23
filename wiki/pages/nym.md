---
title: "Nym mixnet"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# Nym

> A mixnet that adds cover traffic and random delays to packets (Loopix
> design) so that even an observer watching the whole network cannot easily
> link sender and receiver. Nodes are paid in the NYM token; NymVPN offers a
> fast two-hop mode and a slower five-hop mixnet mode.

## Details

- Stronger than Tor against global traffic analysis, at the cost of latency.
- Credentials can be paid anonymously (zk-nyms).

## How it serves the organism

Hides who the organism talks to (its suppliers, peers, children), the
metadata layer that Tor leaves exposed to a global observer
([op-metadata-privacy](op-metadata-privacy.md)).

## How it fails

Latency unsuitable for interactive inference; token-incentivised operator
set; smaller anonymity set.

## Related

[tor-onion-services](tor-onion-services.md) · [i2p](i2p.md) · [location-hiding](location-hiding.md)

## Sources

- Nym — <https://nym.com/>
- Loopix paper (USENIX Security 2017) — <https://www.usenix.org/conference/usenixsecurity17/technical-sessions/presentation/piotrowska>
