---
title: "Cashu ecash"
category: money-rail
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Cashu

> Chaumian ecash backed by Bitcoin: a mint issues blind-signed tokens it
> cannot link to their holder. Tokens are bearer strings, so an agent can pay
> by pasting a token into an HTTP header. Private and simple, but **the mint
> is a custodian**.

## Details

- NUT-11 P2PK and multisig locks; **NUT-28 Pay-to-Blinded-Key** (Nutshell
  0.20.3) hides the receiver's key from the mint.
- **NUT-24** specifies native HTTP-402 ecash (`X-Cashu` header); Blossom
  BUD-07 uses it for paid storage ([blossom](blossom.md)).
- CDK v0.18 (Q3 2026): NUT-25 BOLT12, NUT-16 animated QR, durable melts.
- Used by [routstr](routstr.md) to pay for inference per request.

## How it serves the organism

Private payments for compute and storage with no account; balances are not
visible on any chain ([privacy-organ](privacy-organ.md)).

## How it fails

- The mint can rug or be shut down; spread balances across mints and sweep to
  self-custody ([custodian-seizure](custodian-seizure.md)).
- Bearer tokens: anyone who reads the organism's memory or logs can spend them
  (see [phala-dstack-incident-2026-10](phala-dstack-incident-2026-10.md),
  where env vars were read).

## Related

[fedimint](fedimint.md) · [nip-60-nutzaps](nip-60-nutzaps.md) · [lightning](lightning.md) · [routstr](routstr.md)

## Sources

- Cashu NUTs — <https://github.com/cashubtc/nuts>
- NUT-24 — <https://cashubtc.github.io/nuts/24/>
- NUT-28 — <https://cashubtc.github.io/nuts/28>
- Cashu Q3 2026 highlights — <https://blog.cashu.space/q3-2026-highlights>
