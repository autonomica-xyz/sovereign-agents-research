---
title: "SporeStack (and Slow Servers)"
category: compute
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# SporeStack

> The archetypal machine-buyable VPS: fund a token with XMR, BTC or BCH and
> drive servers through an API reachable over Tor and I2P, with no account.
> EternalSeedBox was built on it. SporeStack raised its minimum to $1,000 on
> 27 Oct 2026 and stopped issuing new tokens on 7 Nov 2026 after someone used
> it to launch 250 masscan servers.

## Details

- Resold DigitalOcean and Vultr capacity, so it never offered confidential
  execution.
- Maintenance mode: existing tokens keep working; the homepage showed a $10
  invite-code path beside a $5,000 self-serve minimum (Nov 2026).
- Same operator runs **Slow Servers** (SSH-based signup, Tor).
- Acceptable-use policy can forfeit a token's balance.

## How it serves the organism

Showed the right interface: an API a program can pay and use anonymously.

## How it fails

It is the clearest [supplier-shutdown](supplier-shutdown.md) case: one
reseller's abuse response ended reproduction for an entire lineage
([eternalseedbox](eternalseedbox.md)).

## Related

[supplier-shutdown](supplier-shutdown.md) · [bitlaunch](bitlaunch.md) · [op-anonymous-confidential-compute](op-anonymous-confidential-compute.md)

## Sources

- SporeStack changelog — <https://api.sporestack.com/changelog>
- Maintenance-mode post (7 Nov 2026) — <https://sporestack.com/blog/posts/2026-11-07-maintenance-mode.html>
- Slow Servers — <https://slowservers.net/>
