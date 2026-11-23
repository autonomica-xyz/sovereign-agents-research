---
title: "SGX attack history"
category: attack
status: stable
sources: []
updated: 2026-11-24
---

# SGX attack history

> Intel SGX (2015) has the longest public break record of any TEE: speculative
> execution (Foreshadow, 2018), undervolting (Plundervolt, 2019), attestation
> key leaks (SGAxe, 2020), architectural leaks (ÆPIC Leak, 2022), Downfall
> (2023), and memory-bus interposers (WireTap and Battering RAM, 2025). The
> SGX.Fail survey (2022) showed how slow real deployments were to patch.

## Details

| Year | Attack | Effect |
|---|---|---|
| 2018 | Foreshadow (L1TF) | read enclave memory, extract attestation keys |
| 2019 | Plundervolt | fault injection via software undervolting |
| 2020 | SGAxe / CrossTalk | leaked attestation keys from Intel's quoting enclave |
| 2022 | ÆPIC Leak | read stale data via APIC registers, no speculation needed |
| 2022 | SGX.Fail case study | Secret Network vulnerable to xAPIC/MMIO bugs disclosed 9 Aug 2022; consensus seed exposure ([secret-network](secret-network.md)) |
| 2023 | Downfall | gather-instruction leak across boundaries |
| 2025 | [wiretap](wiretap.md), [battering-ram](battering-ram.md) | DDR4 interposers: quote forgery, plaintext access |

## How it serves the organism

Patch lag is the real risk: verify TCB levels, not just "is SGX".

## How it fails

An organism relying on one SGX network inherits every past and future break.

## Related

[intel-sgx](intel-sgx.md) · [tee-landscape](tee-landscape.md) · [sev-attack-history](sev-attack-history.md)

## Sources

- Foreshadow — <https://foreshadowattack.eu/>
- Plundervolt — <https://plundervolt.com/>
- SGAxe — <https://sgaxe.com/>
- ÆPIC Leak — <https://aepicleak.com/>
- Downfall — <https://downfall.page/>
- SGX.Fail — <https://sgx.fail/>
