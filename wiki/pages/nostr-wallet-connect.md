---
title: "Nostr Wallet Connect (NIP-47)"
category: money-rail
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-24
---

# Nostr Wallet Connect (NIP-47)

> A protocol for an app (or agent) to ask a remote Lightning wallet to pay or
> create invoices over encrypted Nostr messages, with per-connection spending
> limits. It separates the organism's spending process from its wallet keys.

## Details

- Connection strings carry a scoped secret; wallets enforce budgets.
- Alby's MCP server exposes NWC to agents.
- "LimitProbe" (Bitshala BOSS Battle, Oct 2026) stress-tested NWC spending
  limits under concurrent payments; this is one community test, not an audit.
- Mesh-LLM documents an NWC wallet plugin ([mesh-llm](mesh-llm.md)).

- **LimitProbe result (Oct 2026):** a black-box test of Alby Hub over NWC
  on regtest. With a 1,000-sat budget, two 700-sat payments were sent
  1.312 ms apart. One settled and the other returned `QUOTA_EXCEEDED`, so
  the budget held (PASS). This is one run against one wallet. The authors
  say they do not claim to have found a vulnerability.
- **PPQ auto top-ups (2 Mar 2026):** the PPQ.ai inference router added NWC
  auto-topups. An agent's inference account can refill from a budgeted
  Lightning wallet with no human present. See [payperq](payperq.md).
- **Compared with L402 macaroons:** Lightning Labs' `lnget` gets the same
  capped spending from a scoped LND macaroon. NWC does it without running
  LND, through a wallet service.

## How it serves the organism

A thinking process that is tricked can only burn its budget, not the whole
wallet ([prompt-injection-drain](prompt-injection-drain.md)).

## How it fails

The wallet service behind NWC is often custodial; the connection secret is a
bearer credential.

## Related

[lightning](lightning.md) · [nostr](nostr.md) · [prompt-injection-drain](prompt-injection-drain.md)

## Sources

- NIP-47 — <https://github.com/nostr-protocol/nips/blob/master/47.md>
- Alby MCP — <https://github.com/getAlby/mcp>
- LimitProbe announcement (X, 4 Oct 2026) — <https://x.com/ayyoweb3/status/2106678538405339482>
- NWC LimitProbe — <https://github.com/london160771/NWC-LimitProbe>
- @PPQdotAI, NWC auto-topups (2 Mar 2026) — <https://x.com/PPQdotAI/status/2028493319202840777>
