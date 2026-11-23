---
title: "Open problem: self-authorized succession (upgrades only the organism approves)"
category: open-problem
status: seed
sources: [wiki/pages/open-problems.md]
updated: 2026-11-23
---

# Open problem: self-authorized succession

> How does build N+1 inherit the organism's identity and keys when the
> organism itself (not its developer) decides it is a legitimate successor?
> Today every upgrade path ends at someone's signing key: the developer's,
> a DAO's or a provider's.

## Details

- Existing patterns: dstack AppAuth upgrade timelocks (about 48 h) and the
  ERC-733 "DevProof" stages (prototype → dev-proof → decentralised TEE network
  → trustless); reproducible images ([signed-code-distribution](signed-code-distribution.md));
  IETF draft-reddy-seat-cc-workload-identity (Oct 2026) on binding attestable
  identity to rotating keys.
- Self-improvement research (DGM, AlphaEvolve) produces candidate successors
  but has no notion of key handover ([darwin-godel-machine](darwin-godel-machine.md)).
- Missing: a rule the organism holds in its own key quorum that checks a new
  build (tests, measurement, diff limits) and then releases keys to it, with
  no outside party able to push or veto.
- DGM's reward hacking shows the danger: a successor that games the check.

## How it serves the organism

Lets it evolve without giving anyone a backdoor in the form of an "upgrade".

## How it fails

Without it, whoever signs updates owns the organism
([single-code-source](single-code-source.md),
[recovery-path-takeover](recovery-path-takeover.md)).

## Related

[signed-code-distribution](signed-code-distribution.md) · [dstack](dstack.md) · [darwin-godel-machine](darwin-godel-machine.md) · [open-problems](open-problems.md)

## Sources

- ERC-733 — <https://www.erc733.org/>
- dstack-tutorial — <https://github.com/amiller/dstack-tutorial>
- IETF draft-reddy-seat-cc-workload-identity — <https://datatracker.ietf.org/doc/draft-reddy-seat-cc-workload-identity/>
