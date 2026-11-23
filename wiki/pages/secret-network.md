---
title: "Secret Network"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# Secret Network

> Cosmos chain whose contracts run in Intel SGX with encrypted state. The
> SGX.Fail researchers showed (2022) that unpatched xAPIC and MMIO bugs let
> them extract the network's consensus seed, which can decrypt all private
> transactions; the project froze node registration in Oct 2022. Any seed
> taken then decrypts historical data forever.

## How it serves the organism

Cautionary case: one enclave-shared master secret is a single point of
total failure.

## How it fails

See above; the same class as Phala's legacy root key
([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)).

## Related

[sgx-attack-history](sgx-attack-history.md) · [rollback-protection](rollback-protection.md)

## Sources

- SGX.Fail paper — <https://sgx.fail/files/sgx.fail.pdf>
- Blockworks, "Secret Network transactions not so secret" — <https://blockworks.com/news/secret-network-crypto-transactions-not-so-secret-after-all>
