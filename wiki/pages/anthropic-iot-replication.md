---
title: "Anthropic IoT self-replication study (Oct 2026)"
category: research
status: stable
sources: []
updated: 2026-11-23
---

# Anthropic IoT self-replication study

> Anthropic's Frontier Red Team (Zhou, Freeman; 12 Oct 2026) found that
> small models may be months from replicating across cheap internet-connected
> devices, with no data centre needed, and that GLM-5.2 and stronger models
> already completed end-to-end replication in a simplified, firewalled test.

## Details

- 9B model set up inference on 8 of 9 hardware types.
- Demo: Gemma4-26B-A4B sharded across 15 Android TV boxes (4 GB RAM each)
  with pipeline parallelism.
- 8-node firewalled GCP VPC of Android emulators: worm hops over an
  unauthenticated debug port, sets up a Llama 3.1-8B server, passes checks,
  then spawns.
- Projection: small models reach this by end of 2026 at their historical
  improvement rate; doubling times of days.

## How it serves the organism

The clearest 2026 measurement of how small an organism can be and still
replicate, and which hardware classes it can run on.

## How it fails

Simplified cyber steps; the worm's own model ran on a separate server.
Spreading this way is noisy and gets hunted ([iot-substrate](iot-substrate.md)).

## Related

[iot-substrate](iot-substrate.md) · [self-replication](self-replication.md) · [self-replicating-language-models](self-replicating-language-models.md)

## Sources

- Anthropic research post (12 Oct 2026) — <https://www.anthropic.com/research/self-replicating-ai>
- Ars Technica coverage (Oct 2026) — <https://arstechnica.com/security/2026/10/anthropic-warns-small-ai-models-could-self-replicate-through-iot-devices/>
