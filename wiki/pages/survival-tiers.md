---
title: "Survival tiers (degraded modes)"
category: concept
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Survival tiers

> When money runs low the organism should not just stop. It drops to cheaper
> models and slower heartbeats, signals distress, and only then dies. Conway's
> Automaton is the clearest implementation.

## Details

Automaton's tiers (ARCHITECTURE.md): **high → normal → low_compute** (cheaper
model, slower heartbeat) **→ critical** (distress signals, accepts funding)
**→ dead**. Its lifecycle state machine runs spawning → provisioning → … →
alive → unhealthy → recovering → dead, with a heartbeat daemon that keeps
running while the agent loop sleeps ([conway-automaton](conway-automaton.md)).

EternalSeedBox makes a similar decision every 12 hours per node: renew, spawn,
or sweep funds to a healthier peer before expiring ([eternalseedbox](eternalseedbox.md)).

## How it serves the organism

Stretches runway in a drought and keeps the identity alive while revenue
recovers.

## How it fails

"Accepts funding" in the critical tier makes the organism dependent on donors
again. A public balance tells predators exactly when it is weak
([public-balance-exposure](public-balance-exposure.md)).

## Related

[earn-buy-redeploy-loop](earn-buy-redeploy-loop.md) · [conway-automaton](conway-automaton.md) · [resilience](resilience.md)

## Sources

- Automaton ARCHITECTURE.md — <https://github.com/Conway-Research/automaton/blob/main/ARCHITECTURE.md>
- EternalSeedBox, arXiv 2609.05431 — <https://arxiv.org/abs/2609.05431>
