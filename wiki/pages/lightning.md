---
title: "Bitcoin Lightning"
category: money-rail
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Bitcoin Lightning

> Instant, cheap Bitcoin payments over channels. No account, no KYC, and
> payments are onion-routed. It is the organism's most permissionless rail
> for paying and being paid per call, through [l402](l402.md),
> [cashu](cashu.md) mints and [nostr-wallet-connect](nostr-wallet-connect.md).

## Details

- **Lightning Agent Tools** (Lightning Labs, 11 Feb 2026): skills for agents,
  `lnget` (an HTTP client that pays L402 invoices automatically, with
  `--max-cost` caps), remote signer, scoped macaroons.
- **Wavelength** (mainnet 23 Oct 2026): self-custodial, Ark-like wallet with an
  MCP server, L402 support and receive-only macaroons for agents; 300k-sat
  account cap, VTXO refresh about every two weeks ([ark](ark.md)).
- **pi402** (12 Nov 2026): lets a Pi coding agent pay for inference over L402
  from an embedded Wavelength wallet.
- Spiral is adding Lightning payments to [mesh-llm](mesh-llm.md).

## How it serves the organism

Pay and get paid in seconds without permission; no chargebacks, no account to
close.

## How it fails

- Running a node exposes a pubkey, channel graph and often an IP; liquidity
  management is work.
- Custodial wallets are seizure points ([custodian-seizure](custodian-seizure.md)).
- Measured agent demand over L402 is tiny ([l402](l402.md)).

## Related

[l402](l402.md) · [cashu](cashu.md) · [ark](ark.md) · [lightning-labs](lightning-labs.md) · [privacy-organ](privacy-organ.md)

## Sources

- Lightning Labs, "The Agents Are Here…" (11 Feb 2026) — <https://lightning.engineering/posts/2026-02-11-ln-agent-tools/>
- lightning-agent-tools — <https://github.com/lightninglabs/lightning-agent-tools>
- Wavelength mainnet launch (23 Oct 2026) — <https://lightning.engineering/posts/2026-10-23-wavelength-mainnet-launch/>
- pi402 announcement (12 Nov 2026) — <https://lightning.engineering/posts/2026-11-12-pi-402/>
