---
title: "PayPerQ (PPQ.ai)"
category: compute
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-24
---

# PayPerQ (PPQ.ai)

> A pay-per-use, OpenAI-compatible gateway to 500+ models, with no
> subscription and no email needed. It takes top-ups in Lightning, on-chain
> BTC, Monero, Litecoin, Liquid or card. Agents can automate it in two
> ways: NWC auto-top-up, and account-free L402 payments on some endpoints.
> Since Sep 2026, every chat completion has been served through an attested
> AWS Nitro enclave that PPQ says keeps prompts out of its own reach.

## Details

From PPQ's `llms.txt` and API docs, read 23 Nov 2026:

- **Payments:**
  - Top-ups by API (`/topup/create/{btc-lightning|btc|ltc|lbtc|xmr}`).
  - Monero top-ups from $5 to $10,000.
  - **NWC auto-top-up** refills the balance from a Nostr Wallet Connect
    wallet when it drops below a threshold (announced 2 Mar 2026). See
    [nostr-wallet-connect](nostr-wallet-connect.md).
- **L402 without an account:** image, image-edit, video and data endpoints
  answer `402 Payment Required` with a Lightning challenge, so a caller
  needs no API key. Chat completions still need a funded key. Invoices
  expire after 10 minutes, and replays rejected with HTTP 400 are not
  refunded.
- **Enclave Router (since Sep 2026):**
  - TLS for `/v1/chat/completions` terminates inside a Nitro enclave.
    Only metadata leaves it: credit id, model, token counts, timing, and a
    content-free trace.
  - The enclave code is open source and reproducibly built, and clients can
    pin `PCR0`.
  - PPQ itself notes the guarantee holds only if the client verifies the
    attestation.
- **Privacy tiers** (the `privacyLevel` on each model): `anon` (the
  provider may keep prompts, but requests are "sent without account
  linkage"), `zdr` (route only to
  zero-data-retention endpoints) and `e2e` (`private/*` models inside a TEE,
  so "even the provider cannot read the prompt"). There is also automated
  PII redaction, which PPQ says can miss names.
- **Agent-friendly:** OpenAI Chat and Responses APIs, so it works with
  Claude Code, OpenCode, Cline and similar harnesses.

## How it serves the organism

It is a fallback brain that needs no identity. An organism with Lightning
or Monero can buy frontier inference by the request, refill itself through
NWC within a capped budget, and request `e2e` models so that neither PPQ
nor the model host sees its thoughts. That is close to the full
"rent a mind privately" organ, short of owning the GPU.

## How it fails

- **Upstream visibility:** the Enclave Router hides prompts from PPQ, not
  from the upstream provider. Only `private/*` models are end-to-end.
- **Single throat:** one company can refuse service, freeze balances or
  drop Monero. The enclave runs on AWS. See
  [payment-deplatforming](payment-deplatforming.md).
- **Linkability:** chat still needs an account key, so requests are
  linkable unless the organism rotates credits.

## Related

[routstr](routstr.md) · [l402](l402.md) · [nostr-wallet-connect](nostr-wallet-connect.md) · [aws-nitro-enclaves](aws-nitro-enclaves.md) · [zkapi](zkapi.md)

## Sources

- PayPerQ — <https://ppq.ai>
- PPQ llms.txt — <https://ppq.ai/llms.txt>
- PPQ API docs — <https://ppq.ai/api-docs>
- @PPQdotAI, NWC auto-topups (2 Mar 2026) — <https://x.com/PPQdotAI/status/2028493319202840777>
