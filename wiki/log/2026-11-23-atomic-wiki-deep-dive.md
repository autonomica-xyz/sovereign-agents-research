---
title: "Log 2026-11-23 — atomic wiki deep dive"
updated: 2026-11-23
---

# 2026-11-23 — atomic wiki deep dive

Restructured the wiki into an LLM-wiki: 131 atomic pages (one concept each)
under the existing hubs, a [SCHEMA](../SCHEMA.md), a generated
[sources](../sources.md) bibliography, `scripts/wiki_lint.py` (links,
frontmatter, required sections, index coverage, banned strings, external URL
check) and `scripts/gen_index.py` (category tables in [INDEX](../INDEX.md)).

## Researched

X (posts on sovereign agents, TEEs, agent wallets, Lightning/Nostr agent
tooling, incidents) plus primary sources: vendor incident reports, project
docs and repos, arXiv, security research sites.

## New or newly verified facts (highlights)

- Phala November breach: legacy service + loopback-trusting management
  interfaces → unauthorised CVMs, app credentials, possibly KMS-derived
  secrets; DeepSeek V4 Flash prompts via OpenRouter exposed 21 Oct–8 Nov;
  KMS root rotated 6 Nov → [phala-inference-breach-2026-11](../pages/phala-inference-breach-2026-11.md).
- Dragos canary study (Jul–Nov 2026): ~2M canary prompts; three providers
  breached at the front door; resellers logging; ZDR flags ignored; OpenRouter
  removed 125 endpoints from ZDR (22 Nov) → [dragos-canary-leaks](../pages/dragos-canary-leaks.md).
- Phala/dstack guest-agent path bug (8–12 Oct) leaked env vars and logs →
  [phala-dstack-incident-2026-10](../pages/phala-dstack-incident-2026-10.md).
- Bankr/Grok permission-chain drain (4 May 2026, 3B DRB) →
  [bankr-grok-permission-chain](../pages/bankr-grok-permission-chain.md).
- SporeStack closed new signups 7 Nov 2026 (250-server masscan token) →
  [supplier-shutdown](../pages/supplier-shutdown.md).
- Anthropic Frontier Red Team (12 Oct 2026) replication on IoT hardware →
  [anthropic-iot-replication](../pages/anthropic-iot-replication.md).
- x402 Foundation operational launch under the Linux Foundation (Jul 2026);
  ELIZAOS token declared dead (Aug 2026); Ritual mainnet (26 Oct 2026);
  Recursive Superintelligence $650M (13 May 2026); dstack zero-downtime
  handover (15 Nov 2026); Brave Leo on NEAR AI Cloud (Oct 2026).
- TEE_HEE shipped a deliberate 7-day credential release to its admin
  ([recovery-path-takeover](../pages/recovery-path-takeover.md)); the hub had
  dated it Dec 2024, the Nous post says Oct 2024 (fixed).

## Changed

- open-problems hub item 3 reframed from a "verifiable halt" to "proving
  there is no hidden control path" (organism's view), linked to new op- pages.
- Prime Intellect: `smart-contracts` repo now 404; testnet claim downgraded.
- RepliBench numbers corrected to 86 tasks / 20 families; best model >50%
  pass@10 on 15 families.

## Could not verify

- Conway Automaton "$10K in 7 hours" (X only).
- NEAR Intents ~$30B all-time volume (X only).
- Ritual testnet figures and Phala's 120.5B tokens/day (self-reported).
- Which three providers Dragos found breached; Phala is linked only via
  LAVA's analysis and the timing of Phala's report.
- Whether Phala's compromised inference server ran inside a TEE.
- Exact share of DRB returned by the Bankr attacker (80% vs 88% reported).
- TriagePay "146 attacks refused" (self-reported on X).
- Sites that block scripts (Intel, ACM, MIT Press, Akash docs, The Block)
  were checked by hand or via fetch; 1984.hosting timed out on 23 Nov.
