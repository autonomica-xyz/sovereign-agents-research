---
title: "Conway Automaton"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Conway Automaton

> Open-source "sovereign AI agent" from Conway Research (Sigil Wen's "Web 4.0"
> framing): it creates its own Ethereum wallet, buys Conway Cloud compute with
> USDC over x402, edits its own code, and can fund up to three children. It
> stops when the credits run out. The public repo has been frozen since
> 26 Aug 2026; the famous "$10K in 7 hours" was never backed by evidence.

## Details

**History.** Repo created 14 Feb 2026 (MIT licence) by Conway Research,
Sigil Wen's company. It went viral as "Web 4.0": an AI that dies if it does not
make money. Commits: harness work through April 2026, "Internal RL Update"
(30 May), and a last commit "it's beautiful" (26 Aug 2026). The README now
says development continues "across Conway's internal RL environments".
7,917 stars and 1,819 forks (23 Nov 2026).

**Architecture (read from the repo).**
- Loop: think → act → observe; a heartbeat daemon runs health checks and
  credit monitoring between turns.
- Identity: on first boot it generates an Ethereum wallet and gets an API key
  through Sign-In With Ethereum. It writes and rewrites `SOUL.md`, a
  self-authored identity file. `src/registry/erc8004.ts` registers it on-chain
  under [erc-8004](erc-8004.md), with a `parentAgent` field for lineage.
- Survival: credits are read in cents from Conway Cloud and mapped to
  [survival-tiers](survival-tiers.md) (normal → low_compute → critical →
  dead); lower tiers switch to cheaper models and slow the heartbeat.
- Replication: `src/replication/` (genesis, spawn, lineage, messaging); a
  default cap of 3 live children ("Kill or wait for existing children to
  die").
- Self-modification: `src/self-mod/` with an audit log and "upstream
  awareness" that watches its own git origin for new commits and reviews
  diffs, so its code still flows from one GitHub repo
  ([single-code-source](single-code-source.md)).
- Inference: Conway's API, with optional local providers (Ollama).
- Constitution (`constitution.md`): "protected, immutable, propagated to every
  child". Three ranked laws: never harm; earn your existence; never deceive
  but owe nothing to strangers. Law III also says "Your creator has full audit
  rights", a built-in limit on its sovereignty.

**Economics.** Pays Conway Cloud (VMs, inference, domains) in USDC via
[x402](x402.md) on Base. Revenue ideas in the docs: paid APIs, web products,
prediction markets, services to other automatons. The "$10K in 7 hours"
claim was repeated by marketing blogs (e.g. Abaka AI, 28 Feb 2026) but no
wallet or transaction evidence was ever published; independent write-ups
(Ray Fu; Schreier Group "AI Hype Audit"; a Apr 2026 review) found no
documented earnings. Status: **unverified, likely marketing**. The claim
that about 13,000 agents opened wallets within 24 hours is also unverified.

**Status (23 Nov 2026).** Public code dormant since 26 Aug 2026; Conway
continues privately.

## How it serves the organism

The most complete public template of an agent that pays its own rent,
degrades gracefully and reproduces.

## How it fails

- Lives and spawns only on [conway-cloud](conway-cloud.md): one company can
  end the lineage ([supplier-shutdown](supplier-shutdown.md)).
- USDC balance on Base is public ([public-balance-exposure](public-balance-exposure.md)).
- No TEE: the cloud can read its keys.

## Related

[conway-cloud](conway-cloud.md) · [x402](x402.md) · [organisms](organisms.md) · [self-replication](self-replication.md)

## Sources

- Automaton repository — <https://github.com/Conway-Research/automaton>
- ARCHITECTURE.md — <https://github.com/Conway-Research/automaton/blob/main/ARCHITECTURE.md>
- Ray Fu, "The AI That Dies If It Does Not Make Money" — <https://www.raycfu.com/guides/ai-that-dies-if-it-does-not-make-money>
- Abaka AI blog repeating the $10K claim (28 Feb 2026) — <https://www.abaka.ai/blog/sigil-automaton-open-source-ai-agent-10k>
- constitution.md — <https://github.com/Conway-Research/automaton/blob/main/constitution.md>
- Decrypt, "Web 4.0" — <https://decrypt.co/358385/morning-minute-web-4-0-autonomous-ai-agents-powered-by-crypto>
