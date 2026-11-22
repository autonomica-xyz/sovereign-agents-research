---
title: "The 5 hard open problems"
status: stable
sources: [docs/adversarial-review.md, docs/research-notes.md]
updated: 2026-11-22
---

# Hard open problems

From [adversarial-review.md](../../docs/adversarial-review.md) (steelmanned,
fact-checked) and [research-notes.md](../../docs/research-notes.md).

1. **Backdoor-free key continuity.** Deployable threshold/MPC signing across
   heterogeneous TEEs (SEV-SNP, TDX, ARM CCA/Nitro) where the long-term key
   survives permanent loss of any one vendor, host or custodian minority;
   recovery by attested-enclave quorum only, no human quorum; policy changes
   only through that quorum. What breaks under a TEE.fail-class physical
   compromise of one vendor?
2. **Identity across upgrades.** Verify build N+1 is the legitimate successor
   of N (same identity and keys) without trusting the developer's signing key
   — reproducible builds, measurement transparency log, timelocked on-chain
   upgrade policy. How do emergency patches fit without becoming a bypass?
3. **A verifiable halt that isn't a backdoor.** Can a halt capability be
   publicly declared and attested, able only to stop/freeze (never read, steer
   or move funds), provably the only out-of-band control path, and preserved
   across migration? Candidate: in-enclave predicate checked against an
   on-chain/threshold-signed stop signal. *(Note: the project rejected the
   accountable-custody frame; this is retained as a research question, not a
   framing.)*
4. **Attestation without trusting chip vendors or physical security.** What
   combination of multi-vendor attestation, ZK proofs of inference, or
   optimistic re-execution verifies execution when any vendor's attestation key
   may be extracted? Overhead today for 7B–70B inference; why 0/13
   confidential-inference providers pass end-to-end checks?
5. **Fork-free migration of sealed state.** Move sealed memory and keys across
   vendors/operators with an attested handoff no operator or human can read in
   transit and provable destruction of the source, so the agent can't be
   cloned.

