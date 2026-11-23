---
title: "Vast.ai"
category: compute
status: seed
sources: []
updated: 2026-11-24
---

# Vast.ai

> A GPU marketplace of independent hosts. It accepts crypto through BitPay
> and Crypto.com as prepaid, non-refundable credits; signup needs an email.

## Details

- Hosts range from data centres to individuals; no TEE.
- Death by empty wallet: when credits reach $0, instances stop, and storage
  and data are scheduled for deletion unless the balance is topped up; card
  holders get auto-charged, crypto-only accounts do not. An organism must keep
  a buffer and refill early.
- Coinbase Commerce payments are legacy (no refunds); BitPay and Crypto.com
  are the current crypto routes, and those processors may ask for identity.

## How it serves the organism

Cheap GPUs for non-secret work (batch jobs, public data processing).

## How it fails

No confidentiality: the host sees memory and disk. Payment processors can
impose identity checks.

## Related

[hyperbolic](hyperbolic.md) · [compute](compute.md)

## Sources

- Rent an H100 with crypto (survey, 2026) — <https://gpuwithcrypto.com/rent-h100-with-crypto/>
- Vast.ai billing — <https://docs.vast.ai/documentation/reference/billing>
- Vast.ai billing reference — <https://docs.vast.ai/guides/reference/billing>
