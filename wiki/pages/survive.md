---
title: "Drive 1: Survive"
status: stable
sources: [docs/state-of-the-art.md, docs/research-notes.md]
updated: 2026-11-22
---

# Drive 1: Survive — persistence, key continuity, self-repair

Source: [state-of-the-art.md §Drive 1](../../docs/state-of-the-art.md).
Working pattern: **sealed state, keys from a quorum, released only to the
organism's attested code.**

## 1a. Persistence / rehydration
- dstack KMS: keys derived per app identity, decoupled from CPU; released only
  to attested measurements; policy on-chain. [dstack-TEE/dstack](https://github.com/Dstack-TEE/dstack)
- Arweave AO / HyperBEAM: permanent process state + message log, restorable on
  another node; SEV-SNP nodes.
- Walrus + Seal: ciphertext on Walrus; t-of-n key servers release keys only
  when an on-chain Move policy passes.
- Rollback protection: ROTE, Narrator (~6k updates/s), Nimble (OSDI 23).
- Maturity: storage is production; rollback-safe rehydration is research/prototype.

## 1b. Key continuity (the self)
- NEAR Chain Signatures: MPC in TEEs, 11-of-17 on mainnet.
- TeeDAO: BFT-governed committee of heterogeneous TEEs, proactive secret
  sharing (research prototype).
- FROST (RFC 9591), CMP primitives; RSS threshold sigs in SEV-SNP+TDX (no
  attestation-bound provisioning yet).
- Freysa Keystone: rotation/recovery under a human committee multisig — a
  survival weak point.
- Dead end today: iO-based hardware-free vaults (minutes + hundreds of GB).
- **Nobody has shipped cross-vendor threshold signing with human-free
  attested-quorum recovery.** → [open problems](open-problems.md) #1.

## 1c. Self-repair
- Conway Automaton: lifecycle state machine, heartbeat daemon, edits own code
  in git with a protected constitution.
- EternalSeedBox: every 12h each node renews, spawns a child, or sweeps funds
  to a healthier peer.
- Darwin Gödel Machine: self-rewriting agents with empirical selection
  (SWE-bench 20%→50%).

## Critical path
1. Key continuity across vendors with quorum recovery, no humans.
2. Rehydration only the real organism can perform: attestation-gated release
   from a threshold quorum + rollback-safe state.
3. Self-repair that patches its own image without a developer key.


## Update 2026-11-22 — cross-vendor custody status (research pass 1)

The open problem (human-free cross-vendor attested-quorum recovery) is still
unshipped, but the substrate moved in Oct–Nov 2026:

- NEAR MPC: all signing now in Intel TDX TEEs on mainnet, attested on-chain,
  Trail of Bits audit published (11-of-17; independent tracker shows 16/11
  after a node removal 22 Oct) — [near.org](https://www.near.org/blog/chain-signatures-tee).
  FROST (RFC 9591) added alongside Cait-Sith ECDSA; **no proactive share
  refresh** (resharing only on membership change). Release 3.19.0 (12 Nov)
  removed ECDSA presignatures entirely, closing the TEE-rollback share-leak
  vector Trail of Bits flagged 25 Sep; key-share migration now requires an
  attested destination node — [releases](https://github.com/near/mpc/releases).
- Lit Protocol v3 "Chipotle": execution decoupled from the KMS, key
  orchestration on-chain via TEE root of trust; **verified AMD attestation
  landed 21 Nov** on top of its SGX heritage — first two-vendor attestation
  move by a deployed signing network —
  [chipotle releases](https://github.com/LIT-Protocol/chipotle/releases).
- dstack v0.6.6 (20 Nov): SEV-SNP TCB policy anchored to AMD security
  bulletins (VCEK chip+TCB binding, AMD CRL revocation enforced), key-epoch
  crossing + `dstack-key-recovery` tool for pre-rotation epochs. Recovery is
  still operator/KMS-epoch based — [release](https://github.com/Dstack-TEE/dstack/releases/tag/v0.6.6).
- Freysa sovereign-agents framework docs *specify* automated cross-TEE
  recovery (Shamir shares across TDX/SEV/Nitro/SGX, each verifying requester
  attestation, "no human intervention") — spec only, no shipped
  implementation found — [architecture](https://framework.freysa.ai/sovereign-agents-framework/architecture).
- Deployed analog: Signal SVR v3 recovers backup keys across SGX (Azure),
  SEV-SNP (GCP) and Nitro (AWS) with no human committee — backup keys, not
  signing quorums — [eprint 2026/1108](https://eprint.iacr.org/2026/1108).
- Paper-stage: "Sovereign Execution Consensus" cross-vendor FROST design
  ([Zenodo](https://doi.org/10.5281/zenodo.18135001)).
