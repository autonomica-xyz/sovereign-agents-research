---
title: "Threshold custody (the self as a quorum)"
category: concept
status: stable
sources: [docs/research-notes.md, docs/state-of-the-art.md]
updated: 2026-11-23
---

# Threshold custody

> The organism's long-term key is split into shares held by independent
> machines, ideally on different TEE vendors and owners. No single machine,
> operator or vendor ever holds the whole key, so seizing one host does not
> seize the organism.

## Details

| System | Scheme | Where shares live | Status (Nov 2026) |
|---|---|---|---|
| [near-mpc](near-mpc.md) | Cait-Sith ECDSA + FROST | Intel TDX nodes, 11-of-17 (tracker showed 16 nodes after a removal 22 Oct) | Production |
| [lit-protocol](lit-protocol.md) | Threshold keys (PKPs) | SGX heritage; AMD attestation landed 21 Nov | Production |
| [dstack](dstack.md) KMS | Derived keys, on-chain policy | TDX-centric | Production |
| TeeDAO | Proactive secret sharing, BFT committee | SGX, TDX, Hygon CSV | Research |
| RSS | Threshold ECDSA / FROST / BLS | SEV-SNP and TDX VMs | Research |
| [frostr](frostr.md) | FROST for Nostr keys | User devices | Beta |
| [signal-svr3](signal-svr3.md) | Cross-vendor backup-key recovery | SGX, SEV-SNP, Nitro | Production (backup keys only) |

Primitives: [frost](frost.md) (RFC 9591), CMP threshold ECDSA.

## How it serves the organism

Turns "one stolen enclave = death" into "an attacker must break t machines on
several vendors at once." Shares can be refreshed when members change.

## How it fails

- Nobody has shipped **cross-vendor threshold signing with human-free,
  attestation-gated recovery** ([op-cross-vendor-key-recovery](op-cross-vendor-key-recovery.md)).
- A leaked vendor attestation key lets an attacker join the quorum with fake
  members ([tee-fail](tee-fail.md)).
- NEAR MPC has no proactive share refresh; resharing happens only on
  membership change.
- Implementation bugs: FROSTR bifrost 2.0.2 had a disclosed nonce-reuse issue
  (8 Nov 2026).

## Related

[attestation-gated-key-release](attestation-gated-key-release.md) · [key-encumbrance](key-encumbrance.md) · [anti-twin-quorum](anti-twin-quorum.md) · [survive](survive.md)

## Sources

- [docs/research-notes.md](../../docs/research-notes.md) item 1 (22 Nov 2026).
- TeeDAO, arXiv 2606.04912 — <https://arxiv.org/abs/2606.04912>
- RSS threshold signatures in SEV-SNP+TDX, ePrint 2026/1670 — <https://eprint.iacr.org/2026/1670>
- NEAR MPC releases — <https://github.com/near/mpc/releases>
- RFC 9591 (FROST) — <https://www.rfc-editor.org/rfc/rfc9591>
