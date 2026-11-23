---
title: "Nosana"
category: compute
status: seed
sources: [docs/state-of-the-art.md]
updated: 2026-11-24
---

# Nosana

> A Solana GPU marketplace: anyone can post jobs or register GPU nodes. Jobs
> are paid in NOS or credits from a Solana wallet. No TEE.

## Details

- Open-source Solana programs for jobs and staking.
- Terms bar sanctioned users and harmful jobs.
- Oct 2026 product update: persistent deployments with SSH access, scoped
  API keys (read-only keys for monitoring), and an MCP server so coding agents
  can deploy jobs.
- Protocol revenue is not published; third-party trackers count millions of
  completed jobs (unverified).

## How it serves the organism

Permissionless GPU inference/training jobs paid from a wallet.

## How it fails

No confidential execution, so the node operator sees everything; market
policy can revoke access ([supplier-shutdown](supplier-shutdown.md)).

## Related

[akash](akash.md) · [io-net](io-net.md) · [compute](compute.md)

## Sources

- Nosana programs — <https://learn.nosana.com/programs/start.html>
- Nosana wallet — <https://learn.nosana.com/about/wallet>
- Nosana terms — <https://nosana.com/terms-and-conditions/>
- Nosana Monthly, October 2026 — <https://nosana.com/blog/nosana-monthly-october-2026/>
