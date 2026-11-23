---
title: "Phala November 2026 breach (CVMs + confidential inference)"
category: attack
status: stable
sources: []
updated: 2026-11-23
---

# Phala November 2026 breach

> A second, larger incident: from 21 Oct to 8 Nov 2026 an attacker chained a
> legacy internet-facing service with management interfaces that trusted
> loopback callers. They created unauthorised CVMs, obtained application
> credentials (and possibly KMS-derived secrets for affected apps), and took
> over an inference VM on a new GPU server that was serving production
> traffic without full hardening, exposing in-flight prompts.

## Details

- Affected: DeepSeek V4 Flash 0731 requests routed to Phala by OpenRouter,
  21 Oct 00:00 – 8 Nov 05:35 UTC; owners of affected CVMs.
- Timeline: earliest misuse of stolen data 22 Oct; intrusion detected 5 Nov;
  **KMS root key rotated 6 Nov**; attacker retried afterwards; a third-party
  researcher's evidence arrived 8 Nov; preliminary report 10 Nov; full RCA
  pending (as of 23 Nov).
- Phala's report does not say whether the compromised inference server ran
  inside a TEE.
- Phala's report does not name the researcher; LAVA's write-up links the
  incident to the Dragos canary study
  ([dragos-canary-leaks](dragos-canary-leaks.md)). OpenRouter off-boarded
  three providers and removed 125 endpoints from zero-data-retention
  eligibility (22 Nov 2026).

## How it serves the organism

Hard evidence that "confidential inference" is a promise about one deployment
at a time, and that a provider's **KMS root** is a single point of failure for
every app that derives keys from it.

## How it fails

(For the organism) Its thoughts, API keys and money-bearing tokens sent in a
prompt would have been stolen; KMS-derived secrets may have leaked. Defence:
never put secrets in prompts; spread inference across providers; keep wallet
keys in a quorum not derived from one provider's KMS
([op-inference-confidentiality](op-inference-confidentiality.md)).

## Related

[phala-dstack-incident-2026-10](phala-dstack-incident-2026-10.md) · [dragos-canary-leaks](dragos-canary-leaks.md) · [phala-cloud](phala-cloud.md)

## Sources

- Phala November preliminary incident report (10 Nov 2026) — <https://phala.com/posts/phala-november-preliminary-incident-report>
- OpenRouter, "Data Processing Incidents on Inference Providers" (22 Nov 2026) — <https://openrouter.ai/blog/announcements/data-processing-incidents-on-inference-providers/>
- PrivacyAffairs analysis — <https://www.privacyaffairs.com/phala-openrouter-deepseek-breach/>
