---
title: "TEE landscape (Nov 2026)"
category: reference
status: stable
sources: []
updated: 2026-11-24
---

# TEE landscape

> Every hardware enclave on the market has been broken at least once, and
> all fall to an attacker with physical access to memory. The organism's
> use of TEEs is therefore about raising cost and spreading risk across
> vendors, never trusting one.

## Details

| TEE | Unit | Status for the organism (Nov 2026) | Page |
|---|---|---|---|
| Intel SGX | process enclave | longest attack history; quote key extracted (WireTap) | [intel-sgx](intel-sgx.md), [sgx-attack-history](sgx-attack-history.md) |
| Intel TDX | VM | main choice for dstack, Phala, BuilderNet, ROFL; TEE.fail on DDR5 | [intel-tdx](intel-tdx.md) |
| AMD SEV-SNP | VM | RMPocalypse, Heracles, BadRAM, TEE.fail | [amd-sev-snp](amd-sev-snp.md), [sev-attack-history](sev-attack-history.md) |
| NVIDIA H100/Blackwell CC | GPU | paired with a CPU TEE for confidential inference | [nvidia-confidential-computing](nvidia-confidential-computing.md) |
| Arm CCA | VM (Realm) | little shipping silicon yet | [arm-cca](arm-cca.md) |
| AWS Nitro Enclaves | VM partition | trust in AWS's hypervisor; no memory encryption claim | [aws-nitro-enclaves](aws-nitro-enclaves.md) |
| Google Confidential Space | container on CVM | attestation-gated key release via GCP | [google-confidential-space](google-confidential-space.md) |
| Azure confidential computing | VMs, GPUs | SEV-SNP and TDX VMs, H100 CVMs | [azure-confidential-computing](azure-confidential-computing.md) |

Networks on top: [phala-cloud](phala-cloud.md), [dstack](dstack.md),
[oasis-rofl](oasis-rofl.md), [secret-network](secret-network.md),
[marlin-oyster](marlin-oyster.md), [super-protocol](super-protocol.md),
[iexec](iexec.md), [automata](automata.md), [buildernet-suave](buildernet-suave.md),
[lit-protocol](lit-protocol.md), [near-shade-agents](near-shade-agents.md).

## How it serves the organism

Pick at least two vendors, verify attestation yourself
([remote-attestation](remote-attestation.md)), hold keys by threshold across
them ([threshold-custody](threshold-custody.md)).

## How it fails

Physical attacks, stale TCB acceptance and operator misconfiguration
(Phala's dev-mode KMS) — the last caused the biggest real loss in 2026.

## Related

[op-anonymous-confidential-compute](op-anonymous-confidential-compute.md) · [tee-fail](tee-fail.md) · [phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)

## Sources

- SGX.Fail — <https://sgx.fail/>
- TEE.fail — <https://tee.fail/>
- RMPocalypse — <https://rmpocalypse.github.io/>
