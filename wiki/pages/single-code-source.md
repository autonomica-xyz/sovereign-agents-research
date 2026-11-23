---
title: "Single code source"
category: attack
status: stable
sources: [docs/superorganism-review.md]
updated: 2026-11-23
---

# Single code source

> If every body pulls its code from one place, whoever controls that place
> controls (or kills) the species. Tribler's Mycelium nodes `git pull` from
> one GitHub repo and pin GitHub's IPs in /etc/hosts; one takedown, account
> ban or malicious commit reaches every node.

## Details

- Mycelium checks for updates every 60 s by default (see
  [eternalseedbox](eternalseedbox.md)).
- Two failures in one: deletion (no updates, possibly broken bootstrap) and
  hijack (a pushed update runs everywhere).
- The fix is [signed-code-distribution](signed-code-distribution.md):
  content-addressed images on several networks (Arweave, IPFS, Blossom,
  Nostr), accepted only when the hash matches a rule the organism already
  holds.

## How it serves the organism

Names a control-plane dependency that most agent projects never notice.

## How it fails

(For the organism) GitHub, a registry or a domain owner becomes its
puppeteer.

## Related

[chaindrop-npm-worm](chaindrop-npm-worm.md) · [hugging-face](hugging-face.md) · [signed-code-distribution](signed-code-distribution.md) · [eternalseedbox](eternalseedbox.md) · [nsyte-nsite](nsyte-nsite.md) · [blossom](blossom.md) · [arweave-ao](arweave-ao.md)

## Sources

- Tribler superorganism-experiment repo — <https://github.com/Tribler/superorganism-experiment>
- Wiki review of the repo — [docs/superorganism-review.md](../../docs/superorganism-review.md)
