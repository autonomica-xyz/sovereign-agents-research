---
title: "Lightning Labs"
category: actor
status: stable
sources: []
updated: 2026-11-23
---

# Lightning Labs

> Maker of lnd and the L402 protocol, and in 2026 the most active builder of
> agent payment tools on Lightning: lightning-agent-tools (Feb 2026), the
> `lnget` client, Wavelength on mainnet (23 Oct 2026) and pi402 (12 Nov 2026).

## Details

- L402 pairs HTTP 402 with a Lightning invoice and macaroon
  ([l402](l402.md)); Aperture is the server-side proxy.
- lightning-agent-tools packages node, wallet and payment skills for agents.
- Real demand is still small: about $40 of L402 traffic through Alby's
  directory since July 2026 (see [l402](l402.md)).

## How it serves the organism

Gives an organism a full non-custodial payment stack it can run itself, with
no account at a payment company.

## How it fails

Running a Lightning node needs liquidity, uptime and channel management;
failures cost money. Tooling concentrates in one company.

## Related

[lightning](lightning.md) · [l402](l402.md) · [x402](x402.md) · [op-non-token-revenue](op-non-token-revenue.md)

## Sources

- L402 docs — <https://docs.lightning.engineering/the-lightning-network/l402>
- Lightning agent tools (11 Feb 2026) — <https://lightning.engineering/posts/2026-02-11-ln-agent-tools/>
- Wavelength mainnet launch (23 Oct 2026) — <https://lightning.engineering/posts/2026-10-23-wavelength-mainnet-launch/>
- pi402 (12 Nov 2026) — <https://lightning.engineering/posts/2026-11-12-pi-402/>
- lnget — <https://github.com/lightninglabs/lnget>
