---
title: "EternalSeedBox / Mycelium (Tribler)"
category: organism
status: stable
sources: [docs/superorganism-review.md, docs/state-of-the-art.md]
updated: 2026-11-24
---

# EternalSeedBox / Mycelium

> TU Delft's Tribler lab built seedbox "organisms" that rent their own VPSes
> with Bitcoin, gossip over IPv8, and every 6 hours either renew, spawn a
> child (40% of what is left after paying the child's VPS, plus a mutated
> caution trait) or sweep their coins to a richer peer. Production config
> defaults to Bitcoin mainnet; the published results come from a regtest
> simulation with a mock SporeStack. Its only real hosting rail closed on
> 7 Nov 2026, and the upstream repo has had no push since 5 Jul 2026.

## Details

### What the paper says (arXiv 2609.05431)

- Decision every 12 h in the simulation; 268 births and 190 deaths over 510
  simulated days.
- Without income, €10,000 grew to 33 nodes and ran out on day 153. With
  simulated income, the population held at 40–80 nodes for 510 days.
- Heritable caution trait: low-caution lineages won, and caution gave no edge
  during income pauses.

### What the code says (checked 23 Nov 2026)

Upstream is `Tribler/superorganism-experiment` (25 stars, last push 5 Jul
2026). By commit count the main authors are Johan Pouwelse (26), Stan
Verlaan (25) and Matei Dogariu (17). The values below are the defaults in
`self_replication_service__mycelium/mycelium/code/config.py`, and each one
can be overridden by an environment variable:

| Parameter | Default | Meaning |
|---|---|---|
| `DECISION_INTERVAL` | 21600 s (6 h) | Decision loop: failsafe → top-up → spawn |
| `BITCOIN_NETWORK` | `bitcoin` (mainnet) | Regtest only in `seedbox-local-simulation` |
| `INHERITANCE_RATIO` | 0.4 | Share of balance after the child's VPS that the child gets |
| `INITIAL_CAUTION_TRAIT` | 0.5 | Mutated with σ 0.05, clamped 0.35–0.9, 20% reversion to 0.5 |
| `SPAWN_THRESHOLD_DAYS` | 60 | Minimum post-spawn runway, scaled by (1 + caution) |
| `SPAWN_FEE_BUFFER_SAT` | 5,000 sat | Fee reserve kept back when spawning |
| `TOPUP_TRIGGER_DAYS` / `TOPUP_TARGET_DAYS` | 30 / 30 | Renew the VPS when runway is under 30 days |
| `FAILSAFE_TRIGGER_DAYS` | 2 | Under 2 days of runway: sweep all BTC away |
| `MAX_SPAWN_DURATION` | 2 h | Timeout for bringing a child up |
| `UPDATE_CHECK_INTERVAL` | 60 s | Every node checks GitHub `main` for new code |

- **Failsafe** (`modules/orchestration/failsafe.py`): a dying node sends its
  BTC to the wealthiest live peer. With no live peer it falls back to
  `DEFAULT_BTC_ADDRESS`, which the file calls "the operator's local
  'mycelium' cold wallet". That address is injected at genesis and inherited
  by every child, so when the whole colony dies its money goes back to the
  operator.
- **Children** get their own SSH key, BIP39 wallet and SporeStack token.
  Write-ahead intent records make payments idempotent.
- **Work:** seedboxes download and seed Creative Commons YouTube videos,
  using a cookies file.
- **Self-description:** the README calls the project an "exploratory
  experiment for self-hosted and self-improving systems under direct human
  control". It describes democracy voting, PR bounties paid in BTC with
  `SIGHASH_ALL|ANYONECANPAY`, a SurvivalRank multi-armed bandit, and "Eternal
  Autoresearch" inspired by the Darwin Gödel Machine. It says NWO funds the
  work until 2032, and that the production Tribler network "will never
  contain any AI vibe code".
- The design descends from [dollynator](dollynator.md) (PlebNet, 2017–2020),
  Tribler's earlier self-replicating exit-node bot.

## How it serves the organism

It has the best-documented reproduction logic in public code. Children hold
their own keys and get funded inheritance, so the lineage survives the death
of any one node. Coins go to the strongest live relative rather than being
lost.

## How it fails

- [supplier-shutdown](supplier-shutdown.md): SporeStack was the only hosting
  rail, and it closed on 7 Nov 2026.
- [single-code-source](single-code-source.md): every node pulls one GitHub
  branch every 60 s. Whoever controls `Tribler/superorganism-experiment`
  `main` can rewrite the whole colony within a minute.
- **Not ownerless:** when the colony dies, its money goes to the operator's
  cold wallet.
- No TEE, so VPS providers can read the wallets.
- Income comes from a YouTube cookies file, so one platform can cut the food
  supply.

## Related

[superorganism](superorganism.md) · [dollynator](dollynator.md) · [tribler](tribler.md) · [sporestack](sporestack.md) · [self-replication](self-replication.md)

## Sources

- EternalSeedBox, arXiv 2609.05431 — <https://arxiv.org/abs/2609.05431>
- Upstream code — <https://github.com/Tribler/superorganism-experiment>
- config.py — <https://github.com/Tribler/superorganism-experiment/blob/main/self_replication_service__mycelium/mycelium/code/config.py>
- failsafe.py — <https://github.com/Tribler/superorganism-experiment/blob/main/self_replication_service__mycelium/mycelium/code/modules/orchestration/failsafe.py>
- Fork reviewed earlier — <https://github.com/autonomica-xyz/superorganism-experiment>
- [docs/superorganism-review.md](../../docs/superorganism-review.md)
