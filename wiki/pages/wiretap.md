---
title: "WireTap (DDR4 passive interposer on SGX)"
category: attack
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# WireTap

> 2025 (ACM CCS 2025): a passive interposer on a DDR4 bus captured server
> SGX's deterministic memory ciphertext and recovered the Quoting Enclave's
> ECDSA attestation key, so attackers can forge SGX quotes.

## Details

- Passive: only reads the bus, so it is hard to detect.
- Hit SGX-based networks; Secret Network was cited among affected targets on
  X at the time.

## How it serves the organism

Another reason never to trust one vendor's attestation as proof of safety.

## How it fails

(For the organism) Forged quotes let impostors receive its keys or join its
quorum. See [tee-fail](tee-fail.md) for defences.

## Related

[battering-ram](battering-ram.md) · [tee-fail](tee-fail.md) · [intel-sgx](intel-sgx.md)

## Sources

- wiretap.fail — <https://wiretap.fail/>
- ACM CCS 2025 paper — <https://dl.acm.org/doi/10.1145/3719027.3765204>
