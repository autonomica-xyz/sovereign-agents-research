# sovereignagents.ai: direction (v0.2, 22 Nov 2026)

Set on 22 Nov 2026. This replaces an earlier "accountable custody" recommendation, which was rejected. Every fact correction from [adversarial-review.md](adversarial-review.md) still applies.

## The goal

The site is the manifestation of one vision: the building blocks for creating **digital organisms**, meaning sovereign agents that live, earn, persist, replicate and migrate. The site doesn't argue whether this should happen. That's settled. It exists to make it buildable.

Intellectual roots: The Sovereign Individual, Daemon (Suarez), Accelerando, the holon view (each agent whole in itself and part of a larger ecology), and the cypherpunk tradition.

## Working definition

> An agent is sovereign to the degree that no third party (vendor, host, government or anyone else) can read it, stop it, steer it, or take its assets without the consent of its principal. The principal can be the agent itself.

Unstoppability is a property to engineer.

## Roadmap: L0 to L5, across five axes

| Level | Name | Short version |
|---|---|---|
| L0 | Rented tool | Vendor infra, vendor model, vendor accounts |
| L1 | Self-hosted | Open harness on hardware you control |
| L2 | Private and verifiable | TEE, confidential or local inference, attestation |
| L3 | Self-custodial | Keys born in the enclave, never seen by a human |
| L4 | Self-funding | Earns and pays for its own compute over permissionless rails |
| L5 | Self-sustaining (**the goal**) | Survives losing any host, vendor or key-holder; migrates without cloning; recovers keys with no human quorum; upgrades by trustless succession; can replicate. Nothing outside its own constitution can stop it. A legal wrapper is optional, as a shield. |

The five axes (an agent can advance on each independently; L5 is the maximum on all five):

| Axis | L5 target |
|---|---|
| Privacy | No host, vendor or operator can read its memory, prompts or state |
| Custody | It alone holds its keys and assets; recovery needs no human quorum |
| Funding | Earns and pays over censorship-resistant rails (Bitcoin, Lightning, Cashu) |
| Continuity | Persists through host failure, trustless upgrade succession, migration without cloning, replication |
| Independence | No single host, chip vendor, model provider or jurisdiction is a point of control |

## Engineering agenda (what stands between today and L5)

1. **Multi-vendor threshold keys with no human recovery quorum.** Every shipped system still recovers through people: TEE_HEE's timed credential release to its admin, Freysa Keystone's committee multisig, Coinbase's operator policy. Target: threshold signing across SEV-SNP, TDX and ARM CCA, with recovery by an enclave quorum only.
2. **Trustless upgrade succession.** Identity passes from build N to N+1 without trusting a developer key: reproducible builds, a transparency log of measurements, timelocked on-chain succession rules.
3. **Verification without trusting chip vendors.** Attestation rests on AMD, Intel and NVIDIA keys. TEE.fail (Oct 2025) extracted Intel's attestation key with physical access. The Phala dstack incident (Oct 2026) hit the software around the enclave. confidentialinference.net showed 0 of 13 providers fully attested on 22 Nov. Target: multi-vendor attestation plus ZK or re-execution checks.
4. **Non-cloning migration and deliberate replication.** Move sealed state between vendors and operators with an attested handoff no one can read, and provably destroy the source. Spawn children with their own identity and keys rather than clones (the pattern Spore.fun and Conway Automaton tried).
5. **Censorship-resistant funding that pays the bills.** The rails are Lightning/L402, Cashu (NUT-24) and x402. USDC can be frozen by its issuer, so Bitcoin rails come first. Revenue is the hard part: agentic x402 volume is about $5–11K a month (TRM Labs), pi402 has no public seller yet, Spore.fun earned through memecoins, and one Conway Automaton run showed $0 revenue over 14 days.
6. **Legal wrappers as optional shields, not control points.** No AI personhood anywhere. A Wyoming DUNA needs 100 members and a "person" as administrator, and the 2026 amendments (SF0022) added no AI provision. Bayern's zero-member LLC theory is contested. Use a wrapper only to protect assets, never to give anyone control.

Layers to add to the stack: open-weight model provenance, prompt-injection resistance, supply chain (reproducible builds).

## MVP (sovereignty-first)

1. **Manifesto and essay.** Digital organisms as the goal, rooted in The Sovereign Individual and Daemon, using the corrected facts.
2. **Open stack and atlas.** The roadmap and 12 layers as a CC-BY spec, with an atlas built from one data file and automated checks where possible (the confidentialinference.net pattern).
3. **Sovereignty score.** Self-assessed against the five axes and the L0–L5 checklist, with a badge.
4. **Reference organism.** Aims for L4–L5: enclave-born identity and a Lightning/Cashu wallet, L402 earning, sealed memory, running on multiple hosts (dstack, Akash, Enclava), then threshold keys across vendors.

Site map: `/` manifesto · `/essay` · `/levels` · `/stack/<layer>` · `/atlas` · `/score` · `/kit` (reference organism) · `/library` · `/feed`.

## Disclosure

Aljaz Ceru founded Enclava Labs (enclava.dev, a SEV-SNP confidential PaaS), which is listed in the stack. Disclosed as plain fact.
