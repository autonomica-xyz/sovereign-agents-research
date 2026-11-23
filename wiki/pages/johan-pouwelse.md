---
title: "Johan Pouwelse"
category: actor
status: stable
sources: []
updated: 2026-11-24
---

# Johan Pouwelse

> Associate professor of computer science at TU Delft and founder of
> Tribler. He has led
> the longest-running academic line of self-replicating, self-funding
> software: Dollynator/PlebNet (2017–2020), then the superorganism /
> EternalSeedBox experiment (2025–2026). By commit count he is the top
> author of `Tribler/superorganism-experiment` (26 commits).

## Details

- **Tribler:** a BitTorrent client with Tor-like onion routing
  and its own trust layer (Trustchain/IPv8). See [tribler](tribler.md).
- **Dollynator (2017–2020):** student teams in his lab built exit-node
  bots. They earned bandwidth tokens, sold them for BTC on Tribler's
  decentralized market, bought VPSes through Cloudomate and installed
  children over SSH. See [dollynator](dollynator.md).
- **Superorganism (2025–2026):**
  - Seedboxes rent VPSes from SporeStack with BTC, gossip over IPv8, and
    spawn children with 40% inheritance and a mutating caution trait. The
    upstream repo was last pushed on 5 Jul 2026.
  - The README calls it an "exploratory experiment for self-hosted and
    self-improving systems under direct human control". It says NWO funds
    the work until 2032.
  - It also states that the production Tribler network "will never contain
    any AI vibe code".
  - See [superorganism](superorganism.md) and
    [eternalseedbox](eternalseedbox.md).
- **Design choices from the code:**
  - Every node pulls GitHub `main` every 60 s.
  - A dying colony's coins fall back to "the operator's local 'mycelium'
    cold wallet".
  - Governance is planned through democracy voting and BTC PR bounties.

## How it serves the organism

His lab has run the economic loop of self-replication (work, coin,
server, child) twice, nine years apart. That gives the field its only
longitudinal record of what breaks: thin token markets, checkout scrapers,
and the end of a single hosting supplier.

## How it fails

(As a source) Both projects keep a human hand on the code and the treasury,
by design. Neither published long-run data from mainnet.

## Related

[tribler](tribler.md) · [dollynator](dollynator.md) · [superorganism](superorganism.md) · [eternalseedbox](eternalseedbox.md) · [people-directory](people-directory.md)

## Sources

- superorganism-experiment — <https://github.com/Tribler/superorganism-experiment>
- Dollynator — <https://github.com/Tribler/Dollynator>
- TU Delft profile — <https://www.tudelft.nl/staff/j.a.pouwelse/>
