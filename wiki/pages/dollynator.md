---
title: "Dollynator (PlebNet)"
category: history
status: stable
sources: []
updated: 2026-11-24
---

# Dollynator (PlebNet)

> TU Delft's Tribler lab ran a self-replicating "botnet for good" from 2017
> to 2020. Each bot ran a Tribler exit node and earned bandwidth-reputation
> tokens. It sold them for Bitcoin on Tribler's decentralized market, bought
> its next VPS and VPN through a scraping API (Cloudomate), and installed a
> child over SSH. It is the direct ancestor of
> [eternalseedbox](eternalseedbox.md). Dormant: last push 16 Jul 2020.

## Details

- **Repo:** `Tribler/Dollynator` (formerly PlebNet). LGPL-3.0, 28 stars,
  created 24 Apr 2017, last push 16 Jul 2020. The main committers were
  Matouš Skála, Giorgio Acquati and Jaap Heijligers, all TU Delft student
  teams.
- **Self-description:** "A self-replicating autonomous Tribler exit-node"
  and "an Internet-deployed Darwinian reinforcement learning system based on
  self-replication".
- **Metabolism:** routing anonymised torrent traffic earns MB tokens on
  Trustchain. The bot sells these for BTC on the Tribler market. There are
  three selling strategies (`last_day_sell`, `constant_sell` and
  `simple_moving_average`), and the last one hoards up to 3 days of tokens
  when the price is below its 30-day average.
- **Life cycle:** `plebnet setup` installs a cron job that runs
  `plebnet check` every 5 minutes. The check keeps Tribler alive, picks the
  next provider, sells tokens, and buys the VPS and VPN with
  [Cloudomate](https://github.com/Tribler/cloudomate). Cloudomate is an
  "Unpermissioned Open Computer API" that drives provider checkout pages
  (17 stars, last push Jul 2020). The parent then SSHes into the new box,
  pulls the latest code from GitHub and runs setup. It keeps breeding until
  its own lease ends.
- **Learning:** a modified QD-learning algorithm (Kar, Moura & Poor) picks
  VPS offers. Each bot merges its Q-table with gossiping neighbours'.
  Convergence is prevented by keeping at least 20% weight on its own
  experience. The child inherits the Q-table and the provider offer list.
- **Observation, not control:** an IRC bot answers read-only status queries.
  "Plebnet Vision" draws the family tree.
- **Planned work:** a Q-table to learn "which VPS providers ignore DMCA
  notices and thus do not require VPN".
- **A rigged economy:** a `buybot` could "artificially boost MB demand" by
  matching every bid. The token income was partly subsidised.

## How it serves the organism

It was the first public system to close the loop of useful work, then
token, then BTC, then a new server, then a child, with no human in the
purchase path. Its evolution happened in hosting choice, not in code:
lineages learned which providers let them live.

## How it fails

- **Captcha and checkout drift:** [Cloudomate](https://github.com/Tribler/cloudomate)
  broke whenever a provider changed its checkout page. See
  [supplier-shutdown](supplier-shutdown.md).
- **Thin food supply:** the MB-token market was thin and needed buybot
  support.
- **One code source:** every child cloned GitHub. See
  [single-code-source](single-code-source.md).
- **Abuse exposure:** exit nodes drew abuse complaints, which led to VPN
  dependence and provider bans.

## Related

[eternalseedbox](eternalseedbox.md) · [superorganism](superorganism.md) · [tribler](tribler.md) · [self-replication](self-replication.md) · [timeline](timeline.md)

## Sources

- Dollynator repo — <https://github.com/Tribler/Dollynator>
- Cloudomate — <https://github.com/Tribler/cloudomate>
- Kar, Moura & Poor, QD-learning (IEEE TSP 2013) — <https://doi.org/10.1109/TSP.2013.2241057>
