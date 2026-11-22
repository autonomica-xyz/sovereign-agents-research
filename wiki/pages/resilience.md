---
title: "Drive 3: Resilience"
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-22
---

# Drive 3: Resilience — replication, migration, evolution

Source: [state-of-the-art.md §Drive 3](../../docs/state-of-the-art.md).

## Replication / spawning
- EternalSeedBox: reproduction depends on any node holding a surplus; 268
  births, 190 deaths over 510 simulated days.
- Conway Automaton: up to 3 funded children carrying a hash-checked
  constitution, parent-child messaging.
- Fudan self-replication: Llama3.1-70B 5/10 trials, Qwen2.5-72B 9/10;
  follow-up 11/32 systems.
- RepliBench: obtaining compute is easiest; persisting and passing KYC are
  hardest.

## Migration
- Same-vendor live migration only (Intel MigTD, TALOS, CTR).
- Cross-vendor practical route: redeploy + restore keys from a quorum (dstack
  portable containers with KMS-held keys). → [open problems](open-problems.md) #5.

## Gossip / swarm awareness
Tribler IPv8 (`whoami` gossip), Mesh-LLM gossip, Nostr discovery, libp2p
(Agent Mesh), ContextVM.

## Degraded modes
Automaton survival tiers: high → normal → low_compute (cheaper model, slower
heartbeat) → critical (distress signals, accepts funding) → dead.

## Evolution under real stakes
- EternalSeedBox heritable caution trait: low-caution lineages won; caution
  showed no survival edge during income pauses.
- Spore.fun: TEE agents reproduced at a $500K token valuation; memory-poisoning
  attacks observed.
- Competitive self-evolution selects for deception.
- Sandboxed open-endedness toolbox: Avida, POET, AI-GAs, OMNI, ASAL, AI
  Scientist. None connect agents to real keys or money.

## Critical path
1. Copies sharing a lineage but not keys; quorum/ledger so a stolen twin can't
   spend.
2. Cross-vendor migration without forking.
3. Evolution wired to real revenue and real keys (today: sandboxed or
   token-fed).

