---
title: "Dead ends"
status: stable
sources: [docs/state-of-the-art.md, docs/research-notes.md]
updated: 2026-11-22
---

# Dead ends (ruled out, with reasons)

From [state-of-the-art.md](../../docs/state-of-the-art.md) and
[research-notes.md](../../docs/research-notes.md).

- **Trusting a single TEE vendor** — TEE.fail / WireTap / Battering RAM /
  SGX.fail break each vendor's root; a leaked attestation key lets an attacker
  join a quorum with fake members.
- **iO / witness encryption as a key vault today** — Diamond iO: 15.8 min +
  34.3 GB for a depth-0 circuit; 129 min + 225 GB at depth 10.
- **zkML at 70B** — no published 70B zk proof; zkLLM 13B <15 min is the
  frontier.
- **Proof of deletion as anti-cloning** — impossible to prove; use a
  quorum/ledger that refuses a second live key holder.
- **One code repo, one reseller, one cloud, one relay** — every observed
  kill-vector [organisms](organisms.md).
- **Public on-chain survival balances** — shows predators how close it is to
  death.
- **Treating attestation as proof a host is safe** — it proves a measurement,
  not the host.
- **Rejected framings** — "accountable custody", owner-held halt keys,
  "sovereign ≠ unstoppable" ([record of rejection](../../docs/adversarial-review.md)).

