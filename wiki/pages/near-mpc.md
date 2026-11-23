---
title: "NEAR MPC (Chain Signatures)"
category: technology
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# NEAR MPC (Chain Signatures)

> A production threshold-signing network: an 11-of-17 set of nodes, now all in
> Intel TDX, signs transactions on many chains for NEAR accounts and contracts.
> It is the signing backend of [near-shade-agents](near-shade-agents.md).

## Details

- Cait-Sith threshold ECDSA plus FROST (RFC 9591) for Schnorr/EdDSA chains.
- All signing moved into TDX nodes on mainnet, attested on-chain; Trail of Bits
  audit published.
- Release 3.19.0 (12 Nov 2026) removed ECDSA presignatures, closing a
  TEE-rollback share-leak vector flagged 25 Sep 2026; key-share migration now
  needs an attested destination node.
- An independent tracker showed 16 nodes / threshold 11 after a removal on
  22 Oct 2026.

## How it serves the organism

A ready-made quorum to hold the organism's chain keys, released only to an
agent contract's rules.

## How it fails

- Single vendor (TDX) and a single network with its own governance.
- No proactive share refresh: shares are only re-shared on membership change.
- The agent contract's owner can change guardrails unless the contract is
  locked ([op-self-authorized-succession](op-self-authorized-succession.md)).

## Related

[threshold-custody](threshold-custody.md) · [near-shade-agents](near-shade-agents.md) · [frost](frost.md) · [rollback-protection](rollback-protection.md)

## Sources

- NEAR MPC repo and releases — <https://github.com/near/mpc/releases>
- Chain signatures in TEE (NEAR blog) — <https://www.near.org/blog/chain-signatures-tee>
