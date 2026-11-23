---
title: "Oasis ROFL"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# Oasis ROFL

> Runtime Off-chain Logic: apps run in Intel TEEs (SGX or TDX VMs),
> attest, register on Oasis Sapphire, and get keys from Oasis's
> decentralised key manager. A ROFL marketplace lets providers rent out
> machines for on-chain fees. Mainnet launched 2 Jul 2025, pitched for AI
> agents. By 23 Nov 2026, 184 apps were registered but only 8 had running
> instances, and the Oasis Protocol Foundation hosted almost all of them.

## Details

- **Live registry (Oasis Nexus API, 23 Nov 2026):** 184 ROFL apps
  registered and 8 with active instances: `rofl-scheduler` (3 instances),
  `aster-tee-agent`, `carrot-validator`, `sense-ai-core`, `twap-oracle`,
  `privana`, `privana-services` and `thevault-relay`.
- **Marketplace providers:** 3 in total.
  - The Oasis Protocol Foundation has 6 offers and 14 instances.
  - "Matt's den" has 3 offers and 1 instance.
  - A third provider, registered 10 Nov 2026, has 1 offer and 0
    instances.
- **Model:** an app's policy, stake, encrypted secrets (`sek`) and admin
  live on Sapphire. Instances prove their enclave identity and get keys
  from the key manager. Providers list offers, and apps rent machines and
  pay fees on-chain.
- **SDK:** `oasisprotocol/oasis-sdk` (89 stars) was pushed 23 Nov 2026.

## How it serves the organism

Key release is governed by a contract, and machines are rented on-chain.
An organism can hold its own app admin key, pay for its own instance and
recover secrets on any attested host. In principle this is the cleanest
"body for rent" loop among the TEE chains.

## How it fails

- **One landlord:** 14 of the roughly 15 marketplace instances run on the
  Foundation's provider, so stopping one organisation empties the market.
- **Little real use:** 8 of 184 apps are live.
- **Intel only:** the key manager is itself a TEE committee, and
  SGX/TDX attacks reach it. See [tee-fail](tee-fail.md).

## Related

[tee-landscape](tee-landscape.md) · [phala-cloud](phala-cloud.md) · [attestation-gated-key-release](attestation-gated-key-release.md)

## Sources

- Oasis, ROFL mainnet launch — <https://oasis.net/blog/rofl-mainnet-launch>
- Oasis docs, ROFL — <https://docs.oasis.io/build/rofl/>
- Oasis Nexus API, ROFL apps (23 Nov 2026) — <https://nexus.oasis.io/v1/sapphire/rofl_apps?limit=1000>
- Oasis Nexus API, ROFL market providers (23 Nov 2026) — <https://nexus.oasis.io/v1/sapphire/roflmarket_providers?limit=100>
- ROFL marketplace docs — <https://docs.oasis.io/build/rofl/features/marketplace.md>
