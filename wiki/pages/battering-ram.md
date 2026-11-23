---
title: "Battering RAM (active DDR4 interposer)"
category: attack
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Battering RAM

> Oct 2025, KU Leuven and University of Birmingham: a sub-$50 active DDR4
> interposer that aliases memory addresses after boot checks. It gave
> arbitrary plaintext read/write in SGX, extracted SGX's provisioning key and
> re-enabled an SEV-SNP attestation bypass.

## Details

- Cheap enough that any hosting employee could build one.
- Intel and AMD published guidance; physical attacks remain out of scope.

## How it serves the organism

Sets the price of reading an enclave on DDR4: about $50 and physical access.

## How it fails

(For the organism) Any host with a curious operator is readable. Assume a
landlord can read one body; design so one body holds nothing fatal.

## Related

[wiretap](wiretap.md) · [tee-fail](tee-fail.md) · [amd-sev-snp](amd-sev-snp.md)

## Sources

- batteringram.eu — <https://batteringram.eu/>
- Paper — <https://batteringram.eu/batteringram.pdf>
