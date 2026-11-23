---
title: "Automata (on-chain attestation)"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# Automata

> Automata Network builds on-chain verifiers for TEE attestation: its DCAP
> attestation contracts (v1.1) verify Intel SGX/TDX quotes fully on-chain or
> via a ZK proof of the verification.

## How it serves the organism

Lets a contract check its enclave quote directly, so key release needs no
trusted off-chain verifier.

## How it fails

Gas costs; the contracts still depend on Intel's collateral and revocation
data.

## Related

[remote-attestation](remote-attestation.md) · [tee-landscape](tee-landscape.md)

## Sources

- Automata DCAP attestation docs — <https://docs.ata.network/tee-overview/tee-verifiers/intel-sgx-tdx-dcap/automata-dcap-attestation>
- Repository — <https://github.com/automata-network/automata-dcap-attestation>
