---
title: "Olaoluwa Osuntokun (roasbeef)"
category: actor
status: stable
sources: []
updated: 2026-11-24
---

# Olaoluwa Osuntokun (roasbeef)

> CTO of Lightning Labs (@roasbeef, ~41K followers, Nov 2026). He designed
> L402 in 2020. In 2026 he turned it into the main Bitcoin rail for agents
> with three tools: `lnget`, Aperture with MPP, and pi402, an inference
> stack where a coding agent pays per request over Lightning.

## Details

- **11 Feb 2026:** "waay back in 2020, I designed the L402 protocol to solve
  authentication+payments on the web for machines … flash forward to 2026,
  and now the machines are intelligent". See [l402](l402.md).
- **17 Mar 2026: `lnget`,** "like wget/curl, but agent friendly + L402
  aware". He recommends a scoped LND macaroon "to set an agent budget". [nostr-wallet-connect](nostr-wallet-connect.md) offers the same kind of budget
  over Nostr.
- **20 Mar 2026: `lnget` v1.1.0** supports both MPP and L402, has JSON
  input and output, and adds an MCP server (`lnget mcp serve`).
- **27 Mar 2026: Aperture v0.5.0** serves L402 and MPP. Its agent-friendly
  `aperturecli` lets an agent create services and **set its own prices**.
- **12 Nov 2026: pi402,** "an L402+MPP inference stack built on Pi and
  Aperture … agents can dynamically purchase inference with Bitcoin". It is
  fully open source. He argues: "credit cards are made for humans …
  Bitcoin is made for machines". Builder @dragosd095 noted that with pi402
  "the daily cap in your harness config is now the whole risk policy"
  (15 Nov 2026).
- **Lightning Labs around him:**
  - L402 SDK (15 Apr 2026).
  - An OpenClaw + LND node guide (20 May 2026).
  - A new L402 site (29 Jul 2026).
  - Wavelength on mainnet (23 Oct 2026).
  - See [lightning-labs](lightning-labs.md).

## How it serves the organism

His toolchain covers both halves of the metabolism on one permissionless
rail. The organism can pay for inference and APIs (`lnget`, pi402) and sell
its own services at self-set prices (Aperture), with no account, no KYC
and no card. Macaroon budgets let an organism split its treasury into
capped spending organs.

## How it fails

(As a source) He promotes his company's stack. Receiving L402 payments still
needs a Lightning node with inbound liquidity, which is a hard organ to
grow. See [lightning](lightning.md).

## Related

[l402](l402.md) · [lightning-labs](lightning-labs.md) · [lightning](lightning.md) · [nostr-wallet-connect](nostr-wallet-connect.md) · [people-directory](people-directory.md)

## Sources

- L402 origin (11 Feb 2026) — <https://x.com/roasbeef/status/2021669541559119952>
- lnget (17 Mar 2026) — <https://x.com/roasbeef/status/2033969344770900361>
- lnget v1.1.0 (20 Mar 2026) — <https://x.com/roasbeef/status/2035093669426975093>
- Aperture v0.5.0 (27 Mar 2026) — <https://x.com/roasbeef/status/2037613175168999429>
- pi402 (12 Nov 2026) — <https://x.com/roasbeef/status/2120983638183752053>
- @dragosd095 on pi402 risk (15 Nov 2026) — <https://x.com/dragosd095/status/2121983444938789371>
