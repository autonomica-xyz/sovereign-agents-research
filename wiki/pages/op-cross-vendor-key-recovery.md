---
title: "Open problem: cross-vendor key recovery without humans"
category: open-problem
status: seed
sources: [wiki/pages/open-problems.md]
updated: 2026-11-23
---

# Open problem: cross-vendor key recovery without humans

> The organism's long-term key must survive the loss of any one chip vendor,
> host or provider, and be recoverable only by a quorum of attested enclaves,
> never by a human committee. No deployed system does this as of Nov 2026.

## Details

- Closest analogues: NEAR MPC (TDX only, 11-of-17), Lit Chipotle (SGX and
  AMD attestation), Signal SVR3 (spreads backup secrets across SGX, Nitro and
  SEV-SNP, but for human users), dstack KMS (one provider's root key).
- An attacker stole Phala Cloud's legacy KMS root key on 5 Nov 2026
  ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)): every
  app whose keys were derived from it is permanently exposed, because the
  attacker can re-derive them forever. Apps whose key-release policy lived in
  their own smart contract (dstack's on-chain KMS) were not affected.
- Physical attacks extract attestation keys on Intel and AMD
  ([tee-fail](tee-fail.md)), so one vendor's quorum members can be faked.
- Sub-questions: how to mix vendors in one threshold scheme
  ([frost](frost.md), [threshold-custody](threshold-custody.md)); how to
  rotate members without a human; how to stop a captured provider from
  holding a quorum.

## How it serves the organism

Solving it gives the organism a key that outlives every body and every
supplier.

## How it fails

Partial solutions fall back to a human or a single provider's root key, which
becomes the organism's owner.

## Related

[threshold-custody](threshold-custody.md) · [near-mpc](near-mpc.md) · [lit-protocol](lit-protocol.md) · [signal-svr3](signal-svr3.md) · [open-problems](open-problems.md)

## Sources

- Hub list of hard problems — [open-problems](open-problems.md)
- Phala November detailed report (23 Nov 2026) — <https://phala.com/posts/phala-november-detailed-incident-report>
- Signal SVR3 paper, ePrint 2026/1108 — <https://eprint.iacr.org/2026/1108>
