---
title: "Key encumbrance (Liquefaction)"
category: concept
status: seed
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Key encumbrance

> A key generated inside a TEE and never exported is "encumbered": the human
> who launched the enclave can use it only through rules the enclave enforces,
> and can never take it out. Liquefaction (arXiv 2412.02634) built this for
> blockchain accounts. For the organism, this is the mechanism that makes a
> wallet *its own* rather than its creator's.

## Details

- Liquefaction shows that a key held in an enclave can be shared, rented or
  restricted by policy, which breaks the assumption that "whoever holds the key
  owns the account" (prototype, 2024).
- [tee-hee-he](tee-hee-he.md) applied the same idea to an X account, an email
  account and an Ethereum key in Intel TDX (Dec 2024).
- Encumbrance needs a way to prove the key was generated inside, which is
  remote attestation ([attestation-gated-key-release](attestation-gated-key-release.md)).

## How it serves the organism

Lets an organism prove to counterparties that no human can drain its wallet or
post as it. That matters for anyone who sells to it or funds it.

## How it fails

- A single enclave holding the key is one extraction away from losing it
  ([tee-fail](tee-fail.md)). Combine with [threshold-custody](threshold-custody.md).
- Every account-recovery path is a takeover path
  ([recovery-path-takeover](recovery-path-takeover.md)).

## Related

[tee-hee-he](tee-hee-he.md) · [threshold-custody](threshold-custody.md) · [flashbots](flashbots.md)

## Sources

- Liquefaction, arXiv 2412.02634 — <https://arxiv.org/abs/2412.02634>
- Nous Research, "Setting Your Pet Rock Free" (Dec 2024) — <https://nousresearch.com/setting-your-pet-rock-free>
