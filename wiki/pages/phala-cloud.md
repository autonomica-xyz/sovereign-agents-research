---
title: "Phala Cloud"
category: compute
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Phala Cloud

> A TEE cloud built on [dstack](dstack.md): CVMs on Intel TDX with GPU TEEs,
> paid by card or USDC, plus confidential inference for open-weight models.
> The biggest agent TEE host in 2026, and the source of both of the year's
> real TEE-platform breaches.

## Details

- USDC top-up without a card; CVMs stop when the balance hits $0 (storage
  still billed).
- Served 120.5B confidential-inference tokens in one day (5 Nov 2026, Phala's
  own figure).
- **Oct 2026:** guest-agent bug let an attacker read env vars and logs of some
  apps and steal one gateway token ([phala-dstack-incident-2026-10](phala-dstack-incident-2026-10.md)).
- **Nov 2026:** attacker created CVMs, obtained app credentials and possibly
  KMS-derived secrets, and read in-flight prompts on a new GPU server; KMS root
  key rotated 6 Nov ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)).
- Spore.fun agents and Freysa ran on Phala ([spore-fun](spore-fun.md)).

## How it serves the organism

Buyable confidential bodies with USDC and no card.

## How it fails

- One company's platform, KMS and gateways: a single throat.
- Balance at $0 = stopped body; public USDC balance
  ([public-balance-exposure](public-balance-exposure.md)).
- Platform-layer breaches twice in two months.

## Related

[dstack](dstack.md) · [near-ai-cloud](near-ai-cloud.md) · [akash](akash.md)

## Sources

- Phala Cloud billing — <https://cloud.phala.com/about/billing>
- Phala on X, 120.5B tokens (5 Nov 2026) — <https://x.com/PhalaNetwork/status/2118149437646315926>
- October post-mortem — <https://phala.com/posts/2026-10-post-mortem-dstack-guest-agent-vulnerability>
- November preliminary report (10 Nov 2026) — <https://phala.com/posts/phala-november-preliminary-incident-report>
