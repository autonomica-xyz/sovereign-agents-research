---
title: "zkAPI (anonymous prepaid API credits)"
category: money-rail
status: seed
sources: []
updated: 2026-11-24
---

# zkAPI

> An experimental protocol from Open Anonymity and the Ethereum Foundation
> (repo `vbuterin/zkapi`, created 3 Oct 2026). A caller deposits ETH into a
> vault, then pays an AI or other API per request with zero-knowledge
> proofs. The provider can check that the request is paid for, but cannot
> tell which deposit it came from, so requests cannot be linked to each other
> or to the on-chain wallet. Vitalik Buterin runs it inside his "paranoid
> mode" agent harness, alongside Tor and cover traffic.

## Details

- **Flow** (README, read 23 Nov 2026):
  - Deposit ETH and get a lease for HTTP requests.
  - Provider usage is settled with a signed receipt.
  - Withdraw the rest on-chain. There is a challenge period for stale
    withdrawals.
- **Pieces:**
  - Operator services: `zkapi serverd` (authorisation and Schnorr-signed
    settlement), an indexer for Merkle paths, and a challenge watcher.
  - Clients: a browser SDK, and `zkapi-clientd`, a local OpenAI-compatible
    endpoint.
  - Circuit: `zkapi-v2-note-bound-v1`.
  - Live web app: OA Chat (chat.openanonymity.ai).
- **Trust assumption:** the proving keys come from a **single-party Groth16
  setup**. Whoever ran it could forge proofs. The README calls the protocol
  "experimental".
- **Paranoid mode** (Buterin, 16 Oct 2026):
  - Each conversation gets its own Tor circuit.
  - Requests are masked with random cover traffic.
  - Prompts are rewritten by a local model before they leave the machine
    (he uses "qwen3.8-flash-next").
  - The harness (pi) runs in a bwrap sandbox under torsocks.
  - His own caveat: cover traffic "is okay against passive adversaries but
    much weaker if the LLM provider is colluding with the guard". The task
    "really requires a more specialized mixnet".
- **Repo state:** 83 stars, last push 16 Oct 2026, no licence file
  (GitHub API, 23 Nov 2026).

## How it serves the organism

An organism that buys inference from outside leaks its existence in three
places: the payment, the network path and the prompt. zkAPI cuts the
payment link. Tor or a mixnet blurs the network path, and local rewriting
strips identifying context from the prompt. Together they let a body rent
frontier inference without one provider seeing a continuous identity it
could profile, rate-limit or cut off. See [privacy-organ](privacy-organ.md)
and [op-metadata-privacy](op-metadata-privacy.md).

## How it fails

- **Censorable:** the provider still sees prompt content after rewriting,
  and can refuse service to all zkAPI traffic.
- **Setup trust:** the single-party setup is a trapdoor.
- **ETH-only, few providers:** the organism's inference supply is whatever
  the zkAPI operator has signed up.
- **Timing:** timing correlation by a provider colluding with a Tor guard
  remains, by the author's own account.

## Related

[privacy-organ](privacy-organ.md) · [op-metadata-privacy](op-metadata-privacy.md) · [tor-onion-services](tor-onion-services.md) · [nym](nym.md) · [vitalik-buterin](vitalik-buterin.md) · [x402](x402.md)

## Sources

- zkAPI repo — <https://github.com/vbuterin/zkapi>
- Buterin, "paranoid mode" (X, 16 Oct 2026) — <https://x.com/VitalikButerin/status/2111046730959433793>
- Buterin, self-sovereign LLM setup (2 Apr 2026) — <https://vitalik.eth.limo/general/2026/04/02/secure_llms.html>
