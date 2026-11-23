# 2026-11-24 — Deeper and wider pass

Scope: expand the atomic wiki from 131 to 278 atomic pages (301 files in
`wiki/pages/`), adding history, legal, fiction and reference categories and
new clusters: naming/hosting, P2P networks, decentralized inference and cost
per token, self-improvement, memory and identity, agent economics, wallets
and keys, privacy, TEE landscape, threats, autonomy evals, artificial life,
fiction, and reference pages (timeline, people directory, organism matrix,
L5 checklist, build path, reading list, glossary).

## Resolved since the last pass

- Phala Nov 2026 incident: final report of 23 Nov 2026 gives the full chain
  (Grafana default password → unauthenticated VMM → rootkit; legacy KMS root
  key stolen 4–5 Nov; on-chain-KMS apps unaffected; 2,179 of 2,271 CVMs
  migrated by 21 Nov).
- Dragos canary study providers: GMI Cloud, Together AI, Novita, Atlas Cloud.
- Bankr DRB recovery: 80% (Bankr) to 88% (SlowMist); final share unpublished.
- Conway Automaton's $10K earnings claim: no evidence found (treated as
  marketing).
- 1984 Hosting: all services suspended since 21 Nov 2026 after an intrusion.
- TEE_HEE source repository: blocked by GitHub for ToS on 24 Jan 2025;
  Wayback copy from 25 Dec 2024 survives.

## Still unverified

- Ritual testnet figures; Phala's 120.5B tokens/day; TriagePay counts;
  Chutes' total throughput; Super Protocol's chain status; ERC-8004 counts
  after Jul 2026; Nosana job totals (third-party only).

## Checks

- `python3 scripts/wiki_lint.py` — 0 errors.
- `--external` run; bot-blocked sites (403/429) recorded as check-by-hand.
- Mermaid diagrams rendered with mermaid-cli.
- gitleaks clean.
