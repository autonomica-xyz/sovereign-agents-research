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
- Published 19 Nov 2026 by HD Moore's team. Dragos did not name providers,
  but the providers then disclosed themselves:
  - **Phala**: an attacker read DeepSeek V4 Flash 0731 requests 21 Oct–1 Nov
    and later took the legacy KMS root key
    ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)).
  - **GMI Cloud**: an internal troubleshooting system kept about three days of
    request content; attackers got in on 21–22 Oct and again from 27 Oct
    using two compromised credentials. OpenRouter disabled all GMI endpoints
    on 20 Nov.
  - **Together AI**: an AI coding agent committed a credential (for a private
    Hugging Face repo) while working on a public GitHub repo; someone used it
    to download stored prompt samples from June–July 2026.
  - **Novita**: a routing misconfiguration forwarded some MiniMax requests to
    MiniMax's official API (28 May–11 Nov); a policy breach, not an intrusion.
  - **Atlas Cloud** withdrew its models from OpenRouter pending security
    testing after a third-party incident.
- OpenRouter removed Together AI, Phala and Novita, and pulled 125 endpoints
  from zero-data-retention eligibility (22 Nov 2026).
- Which three are Dragos's "three compromised providers" is inferred, not
  stated: Phala and GMI Cloud are confirmed intrusions; the third is most
  likely Together AI or Atlas Cloud.
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
- BleepingComputer (Nov 2026) — <https://www.bleepingcomputer.com/news/security/openrouter-drops-ai-providers-over-leaked-prompts-and-secrets/>
- Together AI security event — <https://www.together.ai/blog/security-event-prompt-leakage-for-requests-in-june-and-july-of-2026>
- RuntimeWire on GMI Cloud (21 Nov 2026) — <https://runtimewire.com/article/openrouter-cuts-off-gmi-cloud-after-attacker-searched-stored-prompts-for>
- LAVA analysis — <https://lava.security/blog/ai-inference-canary-research-prompts-exposed>
