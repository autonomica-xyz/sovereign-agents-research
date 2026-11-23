---
title: "Holepunch / Pear runtime"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# Holepunch / Pear

> Peer-to-peer stack (Hypercore, Hyperswarm, HyperDHT) behind the Keet
> messenger. The Pear runtime runs and updates apps directly from peers,
> with no servers or app stores: an app is a key, and updates are signed
> appends to its Hypercore log.

## Details

- Hyperswarm finds peers by topic and punches through NATs.
- Hypercore: signed, append-only logs, replicated sparsely.

## How it serves the organism

Code distribution and updates by key without GitHub
([single-code-source](single-code-source.md)); a peer network among its
own bodies.

## How it fails

DHT nodes see IPs; whoever holds the app key controls updates (good if the
organism holds it, fatal otherwise).

## Related

[iroh](iroh.md) · [libp2p](libp2p.md) · [signed-code-distribution](signed-code-distribution.md)

## Sources

- Holepunch — <https://holepunch.to/>
- Pear docs — <https://docs.pears.com/>
