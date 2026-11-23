---
title: "Nostr Wallet Connect (NIP-47)"
category: money-rail
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
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
