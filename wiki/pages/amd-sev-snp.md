---
title: "AMD SEV-SNP"
category: technology
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# AMD SEV-SNP

> AMD's confidential-VM technology (Secure Encrypted Virtualization with Secure
> Nested Paging). It is the second vendor an organism needs so that one
> vendor's broken root of trust is not fatal.

## Details

- Encrypted VM memory plus integrity protection against hypervisor remapping.
- Attestation reports signed by a per-chip key (VCEK) bound to the TCB version.
- dstack v0.6.6 (20 Nov 2026) anchors its SEV-SNP TCB policy to AMD security
  bulletins and enforces AMD's revocation list.
- Lit Protocol added verified AMD attestation on 21 Nov 2026
  ([lit-protocol](lit-protocol.md)); [arweave-ao](arweave-ao.md) HyperBEAM
  nodes can run in SEV-SNP; Signal SVR3 uses it as one of three vendors.

## How it serves the organism

Vendor diversity: key shares split across TDX and SEV-SNP hosts force an
attacker to break both ([threshold-custody](threshold-custody.md)).

## How it fails

- [tee-fail](tee-fail.md) broke SEV-SNP attestation on DDR5;
  [battering-ram](battering-ram.md) re-enabled an SEV-SNP attestation bypass
  on DDR4. AMD will not mitigate physical-access attacks.
- Older TCB versions stay valid unless the verifier checks bulletins.

## Related

[intel-tdx](intel-tdx.md) · [signal-svr3](signal-svr3.md) · [tee-fail](tee-fail.md)

## Sources

- AMD-SB-3040 (TEE.fail) — <https://www.amd.com/en/resources/product-security/bulletin/amd-sb-3040.html>
- dstack v0.6.6 — <https://github.com/Dstack-TEE/dstack/releases/tag/v0.6.6>
- Lit chipotle releases — <https://github.com/LIT-Protocol/chipotle/releases>
