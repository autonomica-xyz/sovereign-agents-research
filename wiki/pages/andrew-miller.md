---
title: "Andrew Miller"
category: actor
status: stable
sources: []
updated: 2026-11-24
---

# Andrew Miller

> Researcher (@socrates1024) and one of the creators of TEE_HEE; the most
> prolific public voice on dstack design. He is also frank about its limits:
> in Oct 2025 he said remote attestation is "not enough" without a provider
> vouching for physical security. In Nov 2026 he demonstrated a zero-downtime
> dstack handover: 0 failed of 503 requests, against a 65 s outage for an
> in-place update.

## Details

- Maintains `dstack-tutorial` (DevProof, timelocks), patterns for apps whose
  operator cannot change them silently ([dstack](dstack.md)).
- Listed as a creator of TEE_HEE ([tee-hee-he](tee-hee-he.md)).
- **28 Oct 2025, after TEE.fail's DDR5 interposer attack:** "just checking
  TDX remote attestation is not enough given the limited threat model, a
  cloud provider w/ reputable physical defense procedures also needs to
  vouch for it." The best-known TEE builder concedes that attestation alone
  does not protect against whoever holds the machine. See
  [tee-fail](tee-fail.md) and
  [op-anonymous-confidential-compute](op-anonymous-confidential-compute.md).
- **Dec 2025:** Teleport's unofficial "TikTok Wrapped" ran account
  delegation inside a dstack TEE with open-source code.
- **5 May 2026:** working on a PR for Nous's hermes-agent "that does e2ee
  verification of TEE-based inference".
- **22 Oct 2026:** dstack is "the open source library for CPU/GPU TEE
  underpinning" Brave Leo's private inference.
- **14 Nov 2026:** highlighted a NEAR hackathon agent "you fund once, with
  any token, via NEAR intents to pay for private inference", with TEE
  verification through the ported `teep` library.
- **15 Nov 2026, zero-downtime handover:** boot a second CVM with the same
  `app_id` and hand state over with a GetKey-sealed handover. On Phala an
  in-place update meant a 65 s outage, while the double-buffered approach
  had 0 failed of 503 requests.

## How it serves the organism

Attested private inference that the agent verifies itself (hermes-agent
e2ee, teep) is the organ that lets a body rent a mind without trusting the
host. His physical-attack caveat marks its limit: an organism that hides
from every provider cannot also get a provider to vouch for its hardware.
Handover without downtime is how a body migrates to a new host and new code
version without dying ([rehydration](rehydration.md)).

## How it fails

(As a source) X threads; results are his own demos.

## Related

[dstack](dstack.md) · [flashbots](flashbots.md) · [tee-hee-he](tee-hee-he.md)

## Sources

- dstack-tutorial — <https://github.com/amiller/dstack-tutorial>
- Zero-downtime handover (X, 15 Nov 2026) — <https://x.com/socrates1024/status/2121830789327282680>
- NEAR hackathon agent (X, 14 Nov 2026) — <https://x.com/socrates1024/status/2121694797106967034>
- Attestation is not enough (X, 28 Oct 2025) — <https://x.com/socrates1024/status/1983225512102179289>
- hermes-agent e2ee PR (X, 5 May 2026) — <https://x.com/socrates1024/status/2051474518082802170>
- Brave Leo on dstack (X, 22 Oct 2026) — <https://x.com/socrates1024/status/2113248826840457306>
