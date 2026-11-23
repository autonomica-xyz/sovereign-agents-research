---
title: "AWS Nitro Enclaves"
category: technology
status: seed
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# AWS Nitro Enclaves

> Isolated VMs inside an EC2 instance, attested by AWS's own signing chain. A
> third TEE "vendor" for key diversity, but one where the attesting party and
> the landlord are the same company.

## Details

- Used by [marlin-oyster](marlin-oyster.md) for a decentralised TEE compute
  market and by [signal-svr3](signal-svr3.md) as one of three vendors.
- Freysa's framework docs list Nitro among the TEEs holding recovery shares
  ([freysa](freysa.md)).

## How it serves the organism

A third independent root for a key quorum, alongside Intel and AMD.

## How it fails

AWS is both host and root of trust and needs an account with identity
checks. It can end the account at will. Use it only as one share among many.

## Related

[threshold-custody](threshold-custody.md) · [marlin-oyster](marlin-oyster.md) · [signal-svr3](signal-svr3.md)

## Sources

- Signal SVR3 cross-vendor paper, ePrint 2026/1108 — <https://eprint.iacr.org/2026/1108>
- Marlin — <https://github.com/marlinprotocol>
