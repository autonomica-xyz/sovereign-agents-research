---
title: "Bitcoin-wiki 'Agents' (julz 2011, Maxwell's StorJ, Hearn 2013)"
category: history
status: stable
sources: []
updated: 2026-11-24
---

# Bitcoin-wiki "Agents" (2011–2013)

> The first complete design of a digital organism. A Bitcoin Wiki page
> describes "an autonomous program that is able to survive by selling services
> for Bitcoins, and using the proceeds to rent server capacity", spawning
> funded children that die when their balance runs out. The idea came from a
> 2011 forum post by "julz", was worked out by Gregory Maxwell using a file
> storage agent called StorJ, and Mike Hearn presented it at the Turing
> Festival in 2013.

## Details

- **Body:** rents servers through APIs that accept bitcoin, controlled by SSH;
  moves when it finds a better deal.
- **Reproduction:** a profitable agent funds a child with a "starter pack of
  coins"; children that do not break even die. This is the
  [earn-buy-redeploy-loop](earn-buy-redeploy-loop.md) 15 years early.
- **Names:** registers itself on Namecoin (`x536ma.storj.bit`), trading BTC
  for NMC on peer-to-peer exchanges ([dns-seizure](dns-seizure.md)).
- **Self-improvement:** buys code from humans on freelancer sites, runs it in
  a sandbox (Java, NativeClient), A/B tests it, and uses dispute mediators.
- **Low-trust protocols:** pays per minute with re-signed, unbroadcast
  transactions; "server brokers" are agents that resell compute to other
  agents; colo providers could sell SSH keys as smart property.
- **Trusted computing:** the page already argues that agents need TPM-style
  remote attestation to trust that a host will not steal their profits, the
  same problem TEEs address today ([attestation-gated-key-release](attestation-gated-key-release.md)).
- StorJ later inspired the real Storj company (decentralised storage), which
  became an ordinary startup, not an agent.

## How it serves the organism

A design checklist that is still mostly correct: rent, sell, replicate, die,
name yourself with a key, buy improvements, distrust hosts.

## How it fails

Assumed providers would sell servers for bitcoin by API forever; in 2026 the
one such supplier organisms used closed its doors ([supplier-shutdown](supplier-shutdown.md)).
Assumed code improvement must come from humans; LLMs changed that.

## Related

[mike-hearn](mike-hearn.md) · [digital-organism](digital-organism.md) · [self-replication](self-replication.md) · [timeline](timeline.md)

## Sources

- Bitcoin Wiki, "Agent" — <https://en.bitcoin.it/wiki/Agents>
- Mike Hearn, "The Future of Money", Turing Festival 2013 (video) — <https://www.youtube.com/watch?v=MVyv4t0OKe4>
