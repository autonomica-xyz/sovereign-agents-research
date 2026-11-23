---
title: "n0 (number 0)"
category: actor
status: stable
sources: []
updated: 2026-11-23
---

# n0

> The company behind [iroh](iroh.md), the Rust library that dials devices by
> public key with hole punching and relay fallback. iroh 1.0 shipped on
> 15 Jun 2026. n0 also showcases Mesh LLM, which pools GPUs over iroh.

## Details

- iroh's node ID is an Ed25519 public key, so a body's address is a key it
  holds, not an IP or domain ([dns-seizure](dns-seizure.md)).
- Relays are operated by n0 by default; self-hosting relays removes that
  dependency.

## How it serves the organism

Connectivity without registrars, static IPs or a central broker.

## How it fails

Default relays are a central point; a startup's runway is a risk to the
default network, though the code is open.

## Related

[iroh](iroh.md) · [mesh-llm](mesh-llm.md) · [spiral](spiral.md)

## Sources

- iroh 1.0 (15 Jun 2026) — <https://www.iroh.computer/blog/v1>
- Mesh LLM on the iroh blog — <https://www.iroh.computer/blog/mesh-llm>
- iroh repo — <https://github.com/n0-computer/iroh>
