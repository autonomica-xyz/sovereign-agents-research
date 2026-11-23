---
title: "Wallet drainers"
category: attack
status: stable
sources: []
updated: 2026-11-24
---

# Wallet drainers

> Phishing kits that trick a wallet into signing approvals, permits or
> delegations that hand over funds. Scam Sniffer counted $83.85M stolen from
> 106,106 victims in 2025 (down 83% from 2024); Permit signatures dominated,
> and two EIP-7702 batch-signature cases in Aug 2025 took $2.54M.

## Details

- An agent that signs whatever its tools or inbox hand it is the perfect
  drainer victim ([prompt-injection-drain](prompt-injection-drain.md)).

## How it serves the organism

Threat model for its own signer: decode and simulate every signature,
refuse unlimited approvals and delegations.

## How it fails

New signature types (7702, Permit2) outrun filters.

## Related

[eip-7702](eip-7702.md) · [session-keys](session-keys.md) · [social-engineering](social-engineering.md)

## Sources

- Scam Sniffer 2025 report — <https://drops.scamsniffer.io/scam-sniffer-2025-crypto-phishing-losses-fall-83-to-84-million/>
