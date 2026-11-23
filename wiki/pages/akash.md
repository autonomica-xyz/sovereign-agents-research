---
title: "Akash Network"
category: compute
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-24
---

# Akash Network

> A permissionless compute marketplace on Cosmos: providers bid on container
> deployments, paid from a wallet. Self-custody deployment is first-class via
> Console Air, and confidential compute (`tee: cpu | cpu-gpu`) exists but is
> still labelled experimental in the docs. The closest thing to a body the
> organism can buy itself.

## Details

- Deploy from a self-custody wallet via CLI/SDK, or Console with a managed
  wallet; an agent skill and MCP server exist.
- Confidential compute: governance calls it production (provider v0.16.0,
  Jul 2026; AEP-83 Final), docs still say experimental; GPU CC awaits NVIDIA
  licensing (Nov 2026).
- Console Air (AEP-84) is live at air.akash.network.
- Usage: Messari's State of Akash Q3 2026 (mid-Oct) reported about $304K of
  quarterly revenue (+73% QoQ), 420 GPUs (+8.5%) and utilisation up 42% QoQ,
  after a year of contraction.
- Token: on 12 Nov 2026 Akash opened a migration portal and AKT began
  trading as an SPL token on Solana.

## How it serves the organism

No KYC, many independent providers, so losing one provider is not losing the
market ([op-anonymous-confidential-compute](op-anonymous-confidential-compute.md)).

## How it fails

- Providers can close leases; the organism must watch and re-bid.
- The managed-wallet path makes Akash Console the custodian.
- Experimental CC means weaker guarantees than the label suggests.

## Related

[phala-cloud](phala-cloud.md) · [nosana](nosana.md) · [compute](compute.md) · [earn-buy-redeploy-loop](earn-buy-redeploy-loop.md)

## Sources

- Akash for AI agents — <https://akash.network/docs/getting-started/ai-agents/>
- Akash confidential compute — <https://akash.network/docs/learn/core-concepts/confidential-compute/>
- Akash Q3 proposal discussion — <https://github.com/orgs/akash-network/discussions/1541>
- Console Air — <https://air.akash.network>
- HOGE Wire, Akash Q3 2026 (20 Oct 2026, citing Messari) — <https://hoge.gg/de/akash-q3-2026-comeback-dezentrale-gpus/>
- HOGE Wire, Akash Solana migration (13 Nov 2026) — <https://hoge.gg/akash-solana-migration-akt-live-2026/>
