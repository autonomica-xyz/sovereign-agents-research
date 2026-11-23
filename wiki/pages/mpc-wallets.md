---
title: "MPC and TEE-backed wallets"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# MPC and TEE-backed wallets

> Wallets where no single machine holds the whole private key: either the
> key is split into shares that sign together by multi-party computation
> (MPC / threshold signatures), or it lives only inside a hardware enclave
> (Turnkey, Privy, Coinbase CDP). For an organism, the question is always who
> runs the other shares or the enclave.

## Details

| Design | Who can sign | Example |
|---|---|---|
| Threshold Schnorr (FROST) | t of n share holders | [frost](frost.md), [frostr](frostr.md), Spark |
| Threshold ECDSA (MPC) | t of n nodes | [near-mpc](near-mpc.md), Lit ([lit-protocol](lit-protocol.md)) |
| Enclave-held key with policy | the vendor's enclave fleet | [turnkey](turnkey.md), [privy](privy.md), [coinbase-agentic-wallet](coinbase-agentic-wallet.md) |
| Smart-contract multisig | owners on-chain | [safe](safe.md) |

- Threshold schemes leave no single key to steal, but signing needs the
  other parties online and honest.
- Enclave wallets are only as strong as the enclave and its operator
  ([tee-fail](tee-fail.md), [phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)).

## How it serves the organism

Spreads the key so that one seized or broken host cannot take its money
([threshold-custody](threshold-custody.md)).

## How it fails

When a single company runs all the shares or the enclaves, it is custody by
another name ([custodian-seizure](custodian-seizure.md)).

## Related

[threshold-custody](threshold-custody.md) · [key-encumbrance](key-encumbrance.md) · [session-keys](session-keys.md)

## Sources

- Turnkey, verifiable key management on AWS Nitro Enclaves — <https://aws.amazon.com/blogs/web3/building-secure-verifiable-blockchain-key-management-on-aws-nitro-enclaves-at-turnkey/>
- Spark FAQ (2-of-3 FROST operators) — <https://docs.spark.money/learn/faq>
