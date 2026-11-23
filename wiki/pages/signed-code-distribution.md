---
title: "Signed, content-addressed code distribution"
category: concept
status: stable
sources: [docs/nostr-blossom-iroh.md, docs/state-of-the-art.md]
updated: 2026-11-23
---

# Signed, content-addressed code distribution

> The organism should fetch its own code by hash from many places, and accept
> only versions its upgrade policy allows. One GitHub repo pulled every minute
> is a kill switch held by whoever controls that repo.

## Details

- **Why:** EternalSeedBox nodes `git pull` one GitHub repo every 60 s
  ([single-code-source](single-code-source.md)).
- **Pieces shipping (Nov 2026):**
  - [nsyte-nsite](nsyte-nsite.md): NIP-5A site manifests mapping paths to
    SHA-256 blobs on [blossom](blossom.md).
  - **npack:** publisher-signed Nostr kind-9900 release events with SHA-256
    artifacts on Blossom and kind-9901 revocations (prototype; v0.11.4 on 21 Nov).
  - **ngit 3.2.0** (19 Nov): publishes its own releases to Nostr/Blossom with
    checksums; GitHub is only a mirror. Its NIP-82-style software records are
    not yet merged upstream.
  - Reproducible images: flashbots-images; transparency logs: Sigstore Rekor.
- **Upgrade gate:** the new image's measurement must match a policy the
  organism (not a developer) controls ([op-self-authorized-succession](op-self-authorized-succession.md)).

## How it serves the organism

Removes the repo, the CDN and the DNS name as choke points, and stops a
compromised maintainer from pushing a lobotomy.

## How it fails

- Whoever holds the publisher key can still push. A threshold-signed release
  key is the fix ([threshold-custody](threshold-custody.md)).
- Popular Blossom servers and Nostr relays can drop content; replicate widely.

## Related

[single-code-source](single-code-source.md) · [body-stack](body-stack.md) · [blossom](blossom.md) · [nostr](nostr.md)

## Sources

- [docs/nostr-blossom-iroh.md](../../docs/nostr-blossom-iroh.md).
- NIP-5A — <https://github.com/nostr-protocol/nips/blob/master/5A.md>
- npack — <https://github.com/imattau/npack>
- ngit changelog — <https://ngit.dev/ngit/changelog/>
- flashbots-images — <https://github.com/flashbots/flashbots-images>
- Sigstore Rekor — <https://github.com/sigstore/rekor>
