---
title: "Dragos canary study: inference providers leaking prompts (2026)"
category: attack
status: stable
sources: []
updated: 2026-11-23
---

# Dragos canary study

> From July to November 2026 Dragos sent about two million prompts containing
> unique URLs and canary AWS keys to AI services and watched where they
> surfaced. It found attackers stealing request data at **three** hosting
> providers (none knew until notified), marketplace resellers logging and
> using customer prompts, and providers ignoring privacy settings.

## Details

- Largest breach: a couple hundred bait AWS keys, each sent once; every request
  in certain late-October windows was stolen, including ones rejected before a
  model ran, so copying happened at the provider's front door.
- Stolen keys were tested within hours, then used to list S3 buckets, search
  secret stores, enable Bedrock models and add IAM users: tens of thousands of
  AWS API calls.
- Some stolen requests were flagged zero-data-retention.
- One actor compromised two providers at once; tooling changed over three
  weeks.
- Dragos did not name the three. LAVA's analysis says HD Moore pointed to
  Phala the day after publication; treat that link as likely, not confirmed
  ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)).
- Resellers on an inference marketplace only had to list a model cheaply and
  enable request logging.

## How it serves the organism

A measured answer to "does my inference provider read my mind?": sometimes
yes, and sometimes an attacker does.

## How it fails

(For the organism) Any secret it ever puts in a prompt, including wallet
material, API keys or host addresses, should be treated as public. Route
inference to attested enclaves, split across providers, or run its own model
([op-inference-confidentiality](op-inference-confidentiality.md)).

## Related

[phala-inference-breach-2026-11](phala-inference-breach-2026-11.md) · [op-inference-confidentiality](op-inference-confidentiality.md) · [routstr](routstr.md)

## Sources

- Dragos blog (Nov 2026) — <https://www.dragos.com/blog/ai-supply-chain-security-canary-tokens>
- Ars Technica (Nov 2026) — <https://arstechnica.com/security/2026/11/a-leaky-ai-supply-chain-is-exposing-secret-user-data-at-an-alarming-rate/>
- LAVA analysis naming Phala — <https://lava.security/blog/ai-inference-canary-research-prompts-exposed>
