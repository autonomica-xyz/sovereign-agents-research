---
title: "Censorship-resistant hosting and naming: map"
category: concept
status: stable
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-24
---

# Censorship-resistant hosting and naming

> An organism needs three things that cannot be taken by one party: a
> **name** others can find, a **place** its data lives, and a **path** to reach
> it. Each layer has options whose identity is a key the organism holds,
> rather than an account at a registrar, host or ISP.

## Details

| Layer | Key-owned options | Account/registry options |
|---|---|---|
| Name | Tor onion address, Nostr npub / [nsyte-nsite](nsyte-nsite.md), [iroh](iroh.md) node ID, I2P b32, Lokinet .loki | [ens](ens.md), [handshake](handshake.md), [namecoin](namecoin.md), DNS |
| Static data | [blossom](blossom.md), [ipfs](ipfs.md) (needs pinning), [arweave-ao](arweave-ao.md) (paid once), [hyphanet](hyphanet.md) | [filecoin](filecoin.md) deals, [walrus-seal](walrus-seal.md) |
| Running code | [icp-canisters](icp-canisters.md) (pay with cycles), [akash](akash.md), [golem](golem.md), [flux](flux.md), own peers via [holepunch-pear](holepunch-pear.md) | VPS ([bitlaunch](bitlaunch.md), [njalla](njalla.md)) |
| Path | [tor-onion-services](tor-onion-services.md), [i2p](i2p.md), [nym](nym.md), [lokinet](lokinet.md), [veilid](veilid.md), [reticulum](reticulum.md), [yggdrasil](yggdrasil.md), [libp2p](libp2p.md) | Public IP + DNS |

- Key-owned names cannot be seized at a registry
  ([dns-seizure](dns-seizure.md)) but are hard for humans to remember.
- Data stays available only while someone serves it: IPFS without pinning
  disappears; Arweave prepays for storage up front; Blossom relies on servers it
  pays ([blossom](blossom.md) BUD-07).
- Running code is the hard part: only ICP canisters and a few markets let
  code pay for its own execution without an account.

## How it serves the organism

A checklist for "no single party can unpublish me": every layer should have
at least two independent options, and at least one owned by key.

## How it fails

Metadata (who connects when) leaks across layers
([op-metadata-privacy](op-metadata-privacy.md)); anonymity networks are slow;
storage networks need payment that leaves traces.

## Related

[location-hiding](location-hiding.md) · [body-stack](body-stack.md) · [dns-seizure](dns-seizure.md) · [host-seizure](host-seizure.md)

## Sources

- Wiki long-form on Nostr, Blossom and iroh — [docs/nostr-blossom-iroh.md](../../docs/nostr-blossom-iroh.md)
- Tor onion services — <https://community.torproject.org/onion-services/>
