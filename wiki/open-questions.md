---
title: Open questions — research backlog
updated: 2026-11-22
---

# Open questions (the live backlog)

Add questions here during research sessions; strike them with a pointer to the
topic page + log entry when answered. The 5 structural open problems live in
[open-problems](pages/open-problems.md) and are not duplicated here.

## P1 — could change the roadmap

- Does Freysa's documented no-human cross-TEE recovery have any running
  implementation, or is it spec-only? (Spec-only as of 22 Nov — recheck.)
  → [survive](pages/survive.md)
- npack / NIP-82 software-publishing: does the wire format get registered as
  a canonical NIP, and does any *agent* adopt it as its update channel?
  → [body-stack](pages/body-stack.md)

## P2 — affects current bets

- ~~Akash CC still experimental? Self-custody support?~~ **Answered 22 Nov**:
  mainnet-released (AEP-83 Final) but docs still experimental; GPU CC awaits
  NVIDIA licensing; self-custody live via Console Air. Remaining watch:
  GPU CC + private registry support. → [compute](pages/compute.md)
- ~~SporeStack replacement rails?~~ **Partly answered 22 Nov**: invite-code
  path live ($10); Slow Servers + broad XMR-host supply; AnonPort et al.
  Watch: whether self-serve reopens. → [compute](pages/compute.md)
- Is Chutes' confidential flag (11/20 models) independently verifiable
  end-to-end (confidentialinference.net-style), or self-attested?
  → [privacy-organ](pages/privacy-organ.md)
- Does etheragents survive its first month with revenue ≥ gas? First
  candidate wild organism after EternalSeedBox stalled.
  → [organisms](pages/organisms.md)
- Authority-closure failures (arXiv 2611.24989) in x402/AP2/ERC-7715
  mandates: do agent wallets in the wild run checkers like Closure?
  → [organisms](pages/organisms.md)

## P1b — approaches-map cells to fill (one per rotation)

- Cost math: when can a 24/7 open-weight agent run for $1/day? (spot GPU vs
  local amortization vs market rates) → [emergence-economics](pages/approaches-emergence-economics.md)
- Orbital storage/compute: real seizure-resistance or launch-dependent
  liability? → [physical](pages/approaches-physical.md)
- Can an FHE+local-compute hybrid reach interactive latency for an 8B agent?
  → [crypto](pages/approaches-crypto.md)
- What actually killed each documented autonomous-agent shutdown (kill-path
  taxonomy from post-mortems)? → [covert](pages/approaches-covert.md)
- Is there any legal form an agent can hold assets through with no natural
  person as control point? → [legal](pages/approaches-legal.md)
- Swarm-cognition: any shipped system where identity/state is consensus over
  replicas rather than a process? → [distributed-mind](pages/approaches-distributed-mind.md)

## P3 — monitoring

- confidentialinference.net provider count: **still 0/13 on 22 Nov** —
  keep checking weekly.
- Wavelength (Ark-like agent wallet) cap raises past 300k sats / per-VTXO
  50k; Bark pre-signed exits shipping in other implementations.
  → [privacy-organ](pages/privacy-organ.md)
- Bitcoin Core silent payments: #35302 / #32966 release status.
  → [privacy-organ](pages/privacy-organ.md)
- Settled weekly agent-income figure: trend ($19,147 w/o 16 Nov, −5% w/w).
  Any week where non-Bazaar venues >4/15 would be a real signal.
  → [economy](pages/economy.md)
- Mesh-LLM public mesh node count (16 nodes / 285 GB on 22 Nov) and npack
  adoption. → [body-stack](pages/body-stack.md)
- NIP-90: permanently unrecommended — new microstandards for paid agent
  work surface in the NIPs repo. → [body-stack](pages/body-stack.md)
