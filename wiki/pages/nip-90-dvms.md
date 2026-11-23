---
title: "NIP-90 Data Vending Machines"
category: technology
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# NIP-90 Data Vending Machines (DVMs)

> A Nostr job market: customers post job requests (kinds 5000–5999), service
> providers return results (6000–6999) and ask for sats. "Money in, data out."
> It is the most permissionless way for an organism to sell work, but demand
> is tiny and the spec is marked unrecommended.

## Details

- Spec status: `draft` `unrecommended` — "this got totally out of control,
  prefer use-case-specific microstandards."
- Nov 2026 census: 380 paid-then-served request/result pairs in 7 days,
  median 21 sats; an independent count found 1,352 DVM requests and **zero**
  with a bid tag ([economy](economy.md)).
- Upstream added NIP-CD "Slash Commands" (kinds 31992/10992) on 21 Oct 2026 as
  a narrower alternative.

## How it serves the organism

No signup, no KYC, paid in Lightning or Cashu: the organism can start earning
the moment it has a key.

## How it fails

Hundreds of sats a week across the whole network does not pay rent
([op-non-token-revenue](op-non-token-revenue.md)). Results are public unless
encrypted.

## Related

[nostr](nostr.md) · [earn-buy-redeploy-loop](earn-buy-redeploy-loop.md) · [economy](economy.md)

## Sources

- NIP-90 — <https://github.com/nostr-protocol/nips/blob/master/90.md>
- DVM census (Nov 2026) — <https://lira-ia.github.io/measure/dvm-census/>
