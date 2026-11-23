---
title: "Intel SGX"
category: technology
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Intel SGX

> Intel's older process-level enclave. It protects a small piece of code
> inside an untrusted OS. It is still used by key networks (Lit's heritage,
> Signal SVR3, Secret Network), and it has the longest record of breaks.

## Details

- Enclaves are small and need special SDKs; Linux workloads usually move to
  [intel-tdx](intel-tdx.md).
- Server SGX on DDR4 uses deterministic memory encryption, which made passive
  bus sniffing useful to attackers.

## How it serves the organism

Small trusted cores (counters, key shares) where a full VM is not needed.

## How it fails

- [wiretap](wiretap.md) (2025): passive DDR4 interposer recovered the
  Quoting Enclave's ECDSA attestation key, so quotes can be forged.
- [battering-ram](battering-ram.md) (2025): a sub-$50 interposer gave
  arbitrary plaintext read/write and extracted SGX's provisioning key.
- SGX.fail (2022) catalogued years of attacks.

## Related

[wiretap](wiretap.md) · [battering-ram](battering-ram.md) · [intel-tdx](intel-tdx.md)

## Sources

- WireTap — <https://wiretap.fail/>
- Battering RAM — <https://batteringram.eu/>
