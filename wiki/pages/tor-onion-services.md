---
title: "Tor onion services"
category: technology
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Tor onion services

> A server reachable at a .onion address without revealing its IP. With
> Onionbalance, one address can front several backends, so the organism can
> keep one public name while its bodies change.

## Details

- Onionbalance publishes one descriptor that points at several backend onion
  services.
- Arti 2.8 (Rust Tor) added vanguards and proof-of-work defences against
  denial of service.
- Some no-KYC hosts take orders over Tor ([sporestack](sporestack.md) API was
  reachable over Tor and I2P).

## How it serves the organism

Hides where its bodies are, and lets it buy and manage hosts without leaking
its own IP ([location-hiding](location-hiding.md)).

## How it fails

- Traffic fingerprinting can still detect and attribute covert channels over
  Tor (ACM IH&MMSec 2025).
- Slow; not suitable for GPU-to-GPU traffic.

## Related

[location-hiding](location-hiding.md) · [iroh](iroh.md) · [approaches-covert](approaches-covert.md)

## Sources

- Onionbalance — <https://onionservices.torproject.org/apps/base/onionbalance/>
- Arti 2.8.0 — <https://blog.torproject.org/arti_2_8_0_released/>
- Tor traffic fingerprinting (ACM IH&MMSec 2025) — <https://dl.acm.org/doi/full/10.1145/3733102.3733140>
