---
title: "NEAR AI"
category: actor
status: stable
sources: []
updated: 2026-11-23
---

# NEAR AI

> The NEAR ecosystem's AI arm. It runs NEAR AI Cloud (confidential inference
> in Intel TDX + NVIDIA GPUs, which serves Brave Leo since Oct 2026), an agent
> market, and works with Shade Agents and NEAR's MPC network for
> keys that no single server holds.

## Details

- Brave pins dstack OS measurements in Leo's verifier
  ([near-ai-cloud](near-ai-cloud.md)).
- Shade Agents get signatures from an agent contract through MPC
  ([near-shade-agents](near-shade-agents.md), [near-mpc](near-mpc.md)).

## How it serves the organism

The most complete stack in production where the keys live in an MPC network
and the code runs attested, so no single host owns the agent.

## How it fails

Depends on NEAR chain governance and on Intel/NVIDIA attestation
([tee-fail](tee-fail.md)).

## Related

[near-ai-cloud](near-ai-cloud.md) · [near-shade-agents](near-shade-agents.md) · [near-mpc](near-mpc.md)

## Sources

- NEAR AI — <https://near.ai/>
- NEAR AI Cloud on Brave Leo — <https://near.ai/blog/near-ai-cloud-brings-private-inference-to-brave-leo>
- NEAR AI agent market — <https://near.ai/blog/introducing-near-ai-agent-market>
