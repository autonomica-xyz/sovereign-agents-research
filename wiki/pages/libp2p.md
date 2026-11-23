---
title: "libp2p"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# libp2p

> Modular networking stack from Protocol Labs: peer IDs are public keys,
> with pluggable transports (TCP, QUIC, WebRTC), NAT traversal, Kademlia DHT
> and gossipsub. Used by IPFS, Ethereum consensus clients, Filecoin and many
> others.

## Details

- Implementations in Go, Rust, JS and more.
- Gossipsub is the standard way to broadcast among many peers.

## How it serves the organism

The default toolkit for a swarm of bodies talking to each other.

## How it fails

DHT and peer exchange reveal IPs; no anonymity by default.

## Related

[iroh](iroh.md) · [ipfs](ipfs.md) · [holepunch-pear](holepunch-pear.md)

## Sources

- libp2p docs — <https://libp2p.io/>
