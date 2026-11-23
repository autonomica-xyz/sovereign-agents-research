---
title: "Routstr"
category: compute
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Routstr

> A decentralised, OpenAI-compatible inference router: providers announce
> models and prices on Nostr, clients pay per request with Cashu ecash. No
> account, no card. `routstrd` runs locally, picks the cheapest provider and
> fails over.

## Details

- routstr-core (provider) and routstrd (client daemon with a Cashu wallet,
  Lightning/NWC funding).
- Provider can be pinned per request (`x-routstr-provider`).

## How it serves the organism

Inference bought privately and per call, from many providers, so no one
provider can starve it. Also a way to **sell** spare inference.

## How it fails

Providers see prompts unless they run in a TEE; provider quality varies;
Cashu mint custody risk ([cashu](cashu.md)).

## Related

[cashu](cashu.md) · [nostr](nostr.md) · [payperq](payperq.md) · [op-inference-confidentiality](op-inference-confidentiality.md)

## Sources

- Routstr docs — <https://docs.routstr.com/overview/>
- routstr-core — <https://github.com/Routstr/routstr-core>
- routstrd — <https://github.com/Routstr/routstrd>
- Cashu blog on Routstr — <https://blog.cashu.space/routstr/>
