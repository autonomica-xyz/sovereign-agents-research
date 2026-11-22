---
title: "Engineering agenda"
status: stable
sources: [docs/direction.md]
updated: 2026-11-22
---

# Engineering agenda: what stands between today and L5

From [direction.md](../../docs/direction.md) (v0.2).

1. **Multi-vendor threshold keys with no human recovery quorum.** Every shipped
   system still recovers through people (TEE_HEE's 7-day admin release, Freysa
   Keystone's committee multisig, Coinbase's operator policy). Target:
   threshold signing across SEV-SNP, TDX, ARM CCA; recovery by enclave quorum
   only. See [open problems](open-problems.md) #1.
2. **Trustless upgrade succession.** Identity from build N to N+1 without
   trusting a developer key: reproducible builds, measurement transparency
   log, timelocked on-chain succession. See [open problems](open-problems.md) #2.
3. **Verification without trusting chip vendors.** TEE.fail extracted Intel's
   attestation key (Oct 2025); Phala dstack incident hit the wrapper (Oct
   2026); confidentialinference.net showed 0/13 providers fully attested on 22
   Nov 2026. Target: multi-vendor attestation + ZK or re-execution checks.
4. **Non-cloning migration and deliberate replication.** Attested handoff of
   sealed state nobody can read, provable destruction of the source, children
   with their own keys (Spore.fun, Conway Automaton pattern).
5. **Censorship-resistant funding that pays the bills.** Lightning/L402, Cashu
   (NUT-24), x402. USDC can be frozen; Bitcoin rails first. Revenue is the
   hard part: agentic x402 ≈ $5–11K/month (TRM Labs); one Conway run showed
   $0 revenue in 14 days.
6. **Legal wrappers as optional shields, never control points.** No AI
   personhood anywhere; Wyoming DUNA needs 100 members and a human
   administrator (2026 amendments added no AI provision); Bayern's zero-member
   LLC theory is contested.

Also to layer in: open-weight model provenance, prompt-injection resistance,
reproducible-build supply chain.

