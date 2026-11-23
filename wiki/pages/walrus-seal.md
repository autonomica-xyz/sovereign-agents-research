---
title: "Walrus + Seal"
category: technology
status: seed
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Walrus + Seal

> Walrus (Mysten Labs) stores blobs across a decentralised storage network;
> Seal is a threshold secrets service whose t-of-n key servers release
> decryption keys only when an on-chain Move policy on Sui approves.

## Details

- The policy is code on Sui: for example "release only to this attested
  enclave" or "only after this payment".
- Key servers are independent operators; the threshold is chosen per policy.

## How it serves the organism

Encrypted memory that only the organism's own policy can unlock, held by a
quorum rather than one operator ([attestation-gated-key-release](attestation-gated-key-release.md)).

## How it fails

Tied to Sui and to the set of Seal key servers; if the policy contract is
upgradable by a developer, that developer can unlock the memory.

## Related

[rehydration](rehydration.md) · [arweave-ao](arweave-ao.md) · [threshold-custody](threshold-custody.md)

## Sources

- Seal — <https://seal.mystenlabs.com/>
- Seal repository — <https://github.com/MystenLabs/seal>
