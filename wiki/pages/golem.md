---
title: "Golem Network"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# Golem Network

> One of the oldest decentralised compute markets (ICO 2016): providers rent
> CPU and GPU to requestors who pay in GLM. Requestors run tasks in VMs on
> providers' machines.

## Details

- No confidential computing by default; providers can see workloads.
- GPU support added later; usage remains small relative to centralised
  clouds.

- **Salad test (13 Jan 2026):** Salad.com, a centralised GPU cloud built on
  consumer GPUs, began mirroring "a portion of its existing commercial
  activity" onto Golem's permissionless execution layer. The goal was to
  test whether customer payments and provider rewards could settle in
  crypto. Salad said it started evaluating DePIN protocols in Q3 2025 and
  found Golem "the closest match". This is an engineering test, not a
  migration.
- **Code:** the `golemfactory/yagna` node daemon was pushed 11 Nov 2026,
  with pre-release v0.18.2-rc5 on 7 Nov 2026. The project is active in
  late 2026.
- Golem's AI page advertises zero-commission GPU provider earnings in GLM
  and Ollama-style model jobs (read Nov 2026).

## How it serves the organism

A permissionless way to rent compute with tokens, no account.

## How it fails

Providers read everything; small capacity; GLM liquidity.

## Related

[akash](akash.md) · [flux](flux.md) · [compute](compute.md)

## Sources

- Golem Network — <https://www.golem.network/>
- Salad × Golem (Chainwire, 13 Jan 2026) — <https://chainwire.org/2026/01/13/salad-com-and-golem-network-partner-to-integrate-web2-workloads-with-decentralized-infrastructure/>
- yagna — <https://github.com/golemfactory/yagna>
- Golem AI — <https://golem.network/ai>
