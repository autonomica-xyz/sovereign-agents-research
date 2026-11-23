---
title: "TEE.fail (DDR5 bus interposer)"
category: attack
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# TEE.fail

> Oct 2025: researchers built a DDR5 memory-bus interposer for under $1,000
> that observes deterministic encrypted memory traffic and extracts
> attestation keys from Intel TDX/SGX and AMD SEV-SNP machines. With those
> keys anyone can forge "genuine" attestation reports. It also showed NVIDIA
> GPU attestation is not bound to a specific CVM.

## Details

- Intel (INTEL-2025-10-28-001) and AMD (AMD-SB-3040) treat physical
  interposer attacks as out of scope and will not mitigate them.
- Consequence: an attacker with one compromised machine can mint
  attestations for fake machines and join a key quorum or receive released
  keys ([attestation-gated-key-release](attestation-gated-key-release.md)).

## How it serves the organism

Kill-vector knowledge: it defines the limits of what a TEE can promise.

## How it fails

(For the organism) Whoever has physical access to its host can read it and
can impersonate attested hosts. Defences: keys split across vendors and
owners, short-lived hot keys, hosts in many places so no single landlord
holds a quorum ([threshold-custody](threshold-custody.md)).

## Related

[wiretap](wiretap.md) · [battering-ram](battering-ram.md) · [intel-tdx](intel-tdx.md) · [amd-sev-snp](amd-sev-snp.md) · [dead-ends](dead-ends.md)

## Sources

- tee.fail (paper and site, Oct 2025) — <https://tee.fail/>
- Intel announcement (28 Oct 2025) — <https://www.intel.com/content/www/us/en/security-center/announcement/intel-security-announcement-2025-10-28-001.html>
- AMD-SB-3040 — <https://www.amd.com/en/resources/product-security/bulletin/amd-sb-3040.html>
- BleepingComputer coverage — <https://www.bleepingcomputer.com/news/security/teefail-attack-breaks-confidential-computing-on-intel-amd-nvidia-cpus/>
