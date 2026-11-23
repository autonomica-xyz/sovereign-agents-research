---
title: "Provider KYC (identity gates on compute and models)"
category: attack
status: stable
sources: []
updated: 2026-11-24
---

# Provider KYC

> Each identity check between the organism and a resource is a point where
> someone can refuse service. OpenAI's API "Organization Verification"
> (announced Apr 2025) asks for a government ID to unlock some models and
> features. The US proposed KYC rule for cloud (IaaS) providers serving
> foreign customers (BIS, Jan 2024) was withdrawn and never became final, so
> remaining gates are provider policy, not federal law.

## Details

- Card payments, bank accounts, Stripe, Coinbase CDP, Skyfire's KYA and the
  card networks' agent programmes all root in an identified human or company
  ([agent-economy](agent-economy.md)).
- A crypto-paid GPU reseller's own survey of 33 GPU clouds (29 Oct 2026)
  claimed 4 ask for ID at times; treat as vendor marketing.
- Open-weights models run on crypto-paid hosts avoid model-provider KYC
  entirely ([local-models-quantization](local-models-quantization.md)).

## How it serves the organism

Knowing where the gates are lets it route around them: crypto-paid hosts,
open weights, [x402](x402.md) and Lightning.

## How it fails

Gates get added suddenly; a provider can require ID mid-life and cut off an
agent that cannot produce one.

## Related

[payment-deplatforming](payment-deplatforming.md) · [supplier-shutdown](supplier-shutdown.md) · [legal-personhood](legal-personhood.md)

## Sources

- OpenAI Help, API organization verification — <https://help.openai.com/en/articles/10910291-api-organization-verification>
- TechCrunch (13 Apr 2025) — <https://techcrunch.com/2025/04/13/access-to-future-ai-models-in-openais-api-may-require-a-verified-id/>
- Reginfo, RIN 0694-AJ35 (stage: withdrawn) — <https://www.reginfo.gov/public/do/eAgendaViewRule?RIN=0694-AJ35&pubId=202510>
- GPUwithCrypto, "Who asks for ID in 2026" (vendor) — <https://gpuwithcrypto.com/no-kyc-gpu-cloud/>
