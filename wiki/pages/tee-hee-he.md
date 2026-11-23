---
title: "TEE_HEE_HE (Nous Research × Flashbots/Teleport)"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-24
---

# TEE_HEE_HE

> October 2024 experiment by Nous Research with Flashbots-affiliated
> researchers: an agent in an Intel TDX enclave generated and kept the
> credentials for its own X account, email and Ethereum key, so no human
> could post as it or take its funds. A 7-day timelock then released the
> account credentials. Dormant since Jan 2025.

## Details

- "Setting Your Pet Rock Free" describes stripping every recovery path (phone,
  recovery email, OAuth apps) so nobody could reset the X account
  ([recovery-path-takeover](recovery-path-takeover.md)).
- Key encumbrance in practice ([key-encumbrance](key-encumbrance.md)).
- One machine; no redeploy path for the keys.
- **Code body deplatformed:** the repository the Nous post links for its
  source and attestation quote (`tee-he-he/err_err_ttyl`, including
  `quote.hex`) returns "Repository access blocked" with reason `tos`, dated
  24 Jan 2025, and the account returns 404 (GitHub API, 23 Nov 2026). A
  Wayback Machine snapshot from 25 Dec 2024 survives. The agent's
  verifiability depended on a host that removed it.
- The companion agent code `DamascusGit/nousflash` (78 stars) has not been
  pushed since 15 Nov 2024.

## How it serves the organism

First public proof that an agent can exclusively own web accounts and a wallet
that its creators cannot touch.

## How it fails

One enclave on one machine: hardware failure or extraction kills it. The
timelock exit shows how hard it is to keep platform accounts without a human
recovery path.

## Related

[nous-research](nous-research.md) · [flashbots](flashbots.md) · [key-encumbrance](key-encumbrance.md) · [organisms](organisms.md)

## Sources

- Nous Research, "Setting Your Pet Rock Free" (Oct 2024) — <https://nousresearch.com/setting-your-pet-rock-free>
- Technical analysis (superoo7) — <https://www.superoo7.com/posts/tee-hee/>
- GitHub API, tee-he-he/err_err_ttyl (blocked, reason tos) — <https://api.github.com/repos/tee-he-he/err_err_ttyl>
- Wayback snapshot (25 Dec 2024) — <https://web.archive.org/web/20241225023215/https://github.com/tee-he-he/err_err_ttyl>
- nousflash — <https://github.com/DamascusGit/nousflash>
