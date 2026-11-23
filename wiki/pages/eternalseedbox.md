---
title: "EternalSeedBox / Mycelium (Tribler)"
category: organism
status: stable
sources: [docs/superorganism-review.md, docs/state-of-the-art.md]
updated: 2026-11-23
---

# EternalSeedBox / Mycelium

> TU Delft's Tribler lab built seedbox "organisms" that buy their own VPSes
> with Bitcoin, gossip over IPv8, and every cycle renew, spawn a child (with
> 40% of reserves and a mutated caution trait) or sweep funds to a healthier
> peer. It ran on regtest Bitcoin with a mock SporeStack and simulated
> income. Its only real hosting rail closed on 7 Nov 2026.

## Details

- Paper (arXiv 2609.05431): decision every 12 h; 268 births and 190 deaths
  over 510 simulated days; without income, €10,000 grew to 33 nodes and ran
  out on day 153; with simulated income, 40–80 nodes for 510 days.
- Code (`self_replication_service__mycelium/`): 6-hourly loop failsafe →
  top-up → spawn; child gets its own SSH key, BIP39 wallet and SporeStack
  token; write-ahead intent records make payments idempotent.
- Heritable caution trait: low-caution lineages won; caution gave no edge in
  income pauses.
- Repo stalled since 5 Jul 2026. Full review: [superorganism](superorganism.md).

## How it serves the organism

The best-documented reproduction logic: children with their own keys, funded
inheritance, a lineage that survives individual deaths.

## How it fails

- [supplier-shutdown](supplier-shutdown.md): SporeStack, the only host rail.
- [single-code-source](single-code-source.md): every node `git pull`s one
  GitHub repo.
- No TEE: VPS providers can read wallets.

## Related

[superorganism](superorganism.md) · [tribler](tribler.md) · [sporestack](sporestack.md) · [self-replication](self-replication.md)

## Sources

- EternalSeedBox, arXiv 2609.05431 — <https://arxiv.org/abs/2609.05431>
- Fork reviewed — <https://github.com/autonomica-xyz/superorganism-experiment>
- [docs/superorganism-review.md](../../docs/superorganism-review.md)
