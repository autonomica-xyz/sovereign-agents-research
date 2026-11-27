---
title: "SporeStack (and Slow Servers)"
category: compute
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-27
---

# SporeStack

> The archetypal machine-buyable VPS: fund a token with XMR, BTC or BCH and
> drive servers through an API reachable over Tor and I2P, with no account.
> EternalSeedBox was built on it. New-token issuance is **open again at a
> $5,000 minimum** ($10 with a code) as of 27 Nov 2026 — the 7 Nov 2026
> maintenance post said "no more new signups", but the homepage copy and
> `POST /token` contradict it.

## Details

- Resold DigitalOcean and Vultr capacity, so it never offered confidential
  execution.
- Token model: a 32–64 char secret is the account. `$5` minimum top-up on an
  existing token; **new tokens: $5,000 minimum**, or **$10 with a
  coupon-style code** (homepage copy, 27 Nov 2026). `POST /token` in
  `api.sporestack.com/openapi.json` = "Creates an invoice for funding a new
  token. Invoice includes your new token." — so new tokens really do issue.
- Same operator runs **Slow Servers** (SSH-based signup, Tor; committed to run
  to ≥2030). The 7 Nov post also says the operator is open to selling
  SporeStack for $100k–$1M.
- API changelog: **2026-11-18 "Affiliate is no more."**; earlier breaking
  changes require an explicit `provider` and `region` on every launch.
- Acceptable-use policy can forfeit a token's balance. Abuse (250 masscan
  servers on a $1,000 token) is what drove the 7 Nov restrictions.

## How it serves the organism

Showed the right interface: an API a program can pay and use anonymously.

## How it fails

It is the clearest [supplier-shutdown](supplier-shutdown.md) case: one
reseller's abuse response ended reproduction for an entire lineage
([eternalseedbox](eternalseedbox.md)).

## Related

[eqvps](eqvps.md) · [supplier-shutdown](supplier-shutdown.md) · [bitlaunch](bitlaunch.md) · [op-anonymous-confidential-compute](op-anonymous-confidential-compute.md)

## Sources

- SporeStack changelog — <https://api.sporestack.com/changelog>
- Maintenance-mode post (7 Nov 2026) — <https://sporestack.com/blog/posts/2026-11-07-maintenance-mode.html>
- Slow Servers — <https://slowservers.net/>
