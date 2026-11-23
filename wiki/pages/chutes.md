---
title: "Chutes"
category: compute
status: seed
sources: []
updated: 2026-11-24
---

# Chutes

> A serverless inference platform (Bittensor ecosystem) whose TEE page
> documents TDX CVMs with GPU attestation; 11 of 20 listed models were flagged
> confidential (Nov 2026).

## Details

- Nonce-bound TDX + GPU attestation per request.
- Traffic: OpenRouter-attributable volume was about 8.3B tokens/day on
  22 Nov 2026 across 8 models, at a weighted $0.167 per million tokens —
  roughly $1.4K/day and $50.4K over 30 days in estimated billings. Chutes'
  own total throughput is reported far higher (hundreds of billions of tokens
  a day, self-reported via Bittensor dashboards).
- Economics: runs as Bittensor subnet 64; miners are paid in subnet emissions,
  which subsidise the low prices.

## How it serves the organism

Another independent confidential-inference supplier, useful for diversity.

## How it fails

Account-based; independent verification of the attestation claims is not yet
public ([op-inference-confidentiality](op-inference-confidentiality.md)).

## Related

[bittensor](bittensor.md) · [nvidia-confidential-computing](nvidia-confidential-computing.md)

## Sources

- Chutes TEE page — <https://chutes.ai/tee>
- Vantage router economics, Chutes (22 Nov 2026) — <https://routers.vantage.sh/providers/chutes>
