---
title: "AMD SEV attack history"
category: attack
status: stable
sources: []
updated: 2026-11-24
---

# AMD SEV attack history

> AMD's confidential VMs have been broken repeatedly: CacheWarp (2023)
> reverted guest writes; BadRAM (Dec 2024) used a ~$10 tamper with the DIMM's
> SPD chip to alias memory and forge attestation; RMPocalypse (ACM CCS 2025)
> showed a single 8-byte write during Reverse Map Table setup breaks SEV-SNP
> on Zen 3/4/5; Heracles (CCS 2025) built a chosen-plaintext attack on
> SEV-SNP's memory encryption; TEE.fail (2025) and Battering RAM hit
> attestation through the memory bus.

## How it serves the organism

Diversify across Intel and AMD so one vendor's break does not expose all
key shares.

## How it fails

AMD treats physical-access attacks as out of scope.

## Related

[amd-sev-snp](amd-sev-snp.md) · [tee-fail](tee-fail.md) · [battering-ram](battering-ram.md) · [sgx-attack-history](sgx-attack-history.md)

## Sources

- CacheWarp — <https://cachewarpattack.com/>
- BadRAM — <https://badram.eu/>
- RMPocalypse — <https://rmpocalypse.github.io/>
- Heracles — <https://heracles-attack.github.io/>
