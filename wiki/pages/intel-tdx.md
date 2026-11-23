---
title: "Intel TDX"
category: technology
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Intel TDX (Trust Domain Extensions)

> Intel's confidential-VM technology: a whole VM ("trust domain") whose memory
> is encrypted and hidden from the hypervisor and host, with a remote
> attestation quote. Most agent TEE stacks in 2026 ([dstack](dstack.md),
> [near-mpc](near-mpc.md), [near-ai-cloud](near-ai-cloud.md)) run on it.

## Details

- Whole-VM isolation, so normal Linux containers run inside (unlike
  [intel-sgx](intel-sgx.md) enclaves).
- Attestation via a quote signed with Intel's provisioning chain; runtime
  measurement registers (RTMRs) record what booted.
- NEAR's MPC network moved all signing into TDX nodes on mainnet in 2026.
- Brave Leo's private chats run in TDX + NVIDIA confidential computing on
  NEAR AI Cloud (from 15 Oct 2026).

## How it serves the organism

The skin: a host operator cannot read the organism's memory, keys or prompts
in normal operation.

## How it fails

- [tee-fail](tee-fail.md) (Oct 2025): a DDR5 bus interposer under $1,000
  extracted attestation keys and forged quotes. Intel considers physical
  attacks out of scope.
- Wrapper software is a bigger day-to-day risk than the silicon
  ([phala-dstack-incident-2026-10](phala-dstack-incident-2026-10.md)).
- Single vendor = single root of trust; pair with [amd-sev-snp](amd-sev-snp.md).

## Related

[amd-sev-snp](amd-sev-snp.md) · [nvidia-confidential-computing](nvidia-confidential-computing.md) · [dstack](dstack.md) · [threshold-custody](threshold-custody.md)

## Sources

- Intel security announcement on TEE.fail (28 Oct 2025) — <https://www.intel.com/content/www/us/en/security-center/announcement/intel-security-announcement-2025-10-28-001.html>
- NEAR chain signatures in TEE — <https://www.near.org/blog/chain-signatures-tee>
- Brave Leo confidential computing (Oct 2026) — <https://brave.com/blog/browser-ai-e2ee/>
