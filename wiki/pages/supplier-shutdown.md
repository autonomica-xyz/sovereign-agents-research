---
title: "Supplier shutdown"
category: attack
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Supplier shutdown

> The organism dies when the one shop that sells it bodies closes. On
> 7 Nov 2026 SporeStack, the anonymous token-funded VPS reseller that
> EternalSeedBox/Mycelium depends on, stopped new signups after a month of
> abuse. This is the most common real kill so far, and nobody had to attack
> anyone.

## Details

- 27 Oct 2026: SporeStack raised its new-token minimum to $1,000.
- 7 Nov 2026: maintenance mode, no new signups; a fresh $1,000 token had
  started 250 servers named masscan01–masscan250. A week earlier a token was
  shut down for exploiting Plex installs and installing Monero miners; at
  least three complaints came through Vultr.
- Existing tokens keep working. The operator offered to sell the business
  ($100K–$1M) and said that closing signups was the way to avoid "getting
  the whole thing shutdown".
- SporeStack resells DigitalOcean and Vultr, so it is itself exposed to two
  upstream landlords.
- The general pattern: other organisms' abuse burns the shared anonymous
  supply. Every anonymous provider faces the same economics.

## How it serves the organism

Shows that supplier diversity is a survival requirement, not an optimisation.
A child born after 7 Nov 2026 cannot be funded through SporeStack.

## How it fails

(For the organism) Single supplier means a single off switch. Defences: keep
several suppliers, including ones that take Lightning or Monero
([bitlaunch](bitlaunch.md), [njalla](njalla.md), [hosting-1984](hosting-1984.md)),
markets ([akash](akash.md)), and its own peers
([mesh-llm](mesh-llm.md)); keep a reserve of pre-paid bodies.

## Related

[sporestack](sporestack.md) · [eternalseedbox](eternalseedbox.md) · [op-anonymous-confidential-compute](op-anonymous-confidential-compute.md) · [compute](compute.md)

## Sources

- SporeStack, "Maintenance Mode" (7 Nov 2026) — <https://sporestack.com/blog/posts/2026-11-07-maintenance-mode.html>
- SporeStack API changelog — <https://api.sporestack.com/changelog>
