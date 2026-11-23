---
title: "Lit Protocol"
category: technology
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Lit Protocol

> A threshold key network: programmable key pairs (PKPs) whose signing is
> governed by "Lit Actions" (JavaScript run by the network). Version 3
> "Chipotle" decouples execution from the key service and, on 21 Nov 2026,
> added verified AMD attestation next to its SGX heritage.

## Details

- PKPs are owned by NFTs or by code; signing happens only if the Lit Action's
  conditions pass.
- The Chipotle release line puts key orchestration on-chain with a TEE root of
  trust; AMD attestation is the first two-vendor move by a deployed signing
  network ([amd-sev-snp](amd-sev-snp.md)).

## How it serves the organism

Lets the organism's wallet sign only under conditions written in code (for
example "only pay hosts on this list", "only release key to this measurement").

## How it fails

- Network governance and node operators are a single community; slashing and
  upgrades are decided outside the organism.
- A PKP owned by an NFT is owned by whoever holds the NFT.

## Related

[threshold-custody](threshold-custody.md) · [near-mpc](near-mpc.md) · [attestation-gated-key-release](attestation-gated-key-release.md)

## Sources

- Lit developer docs — <https://developer.litprotocol.com/>
- Chipotle releases (AMD attestation, 21 Nov 2026) — <https://github.com/LIT-Protocol/chipotle/releases>
