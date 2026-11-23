---
title: "DNS and domain seizure"
category: attack
status: stable
sources: []
updated: 2026-11-23
---

# DNS and domain seizure

> A domain name is a lease from a registry that obeys a government. In
> November 2022 US authorities seized about 249 Z-Library domains in one
> action. An organism reachable only at a domain can be cut off without
> anyone touching its servers.

## Details

- Registries for most gTLDs, and many ccTLDs, follow court orders.
- Privacy registrars such as [njalla](njalla.md) register domains in their
  own name and grant usage rights; that hides the owner but does not stop a
  registry seizure.
- Certificates (ACME) and DNS-API credentials are another control path; the
  Phala October incident included an attacker changing DNS-credential and ACME
  settings on a gateway
  ([phala-dstack-incident-2026-10](phala-dstack-incident-2026-10.md)).
- Addresses that are public keys cannot be seized at a registry: Tor onion
  addresses ([tor-onion-services](tor-onion-services.md)), Nostr npubs and
  nsites ([nsyte-nsite](nsyte-nsite.md)), iroh node IDs ([iroh](iroh.md)).

## How it serves the organism

Pushes the organism's identity and endpoints onto keys it owns.

## How it fails

(For the organism) Its customers, peers and children can no longer find it,
even though it is alive.

## Related

[host-seizure](host-seizure.md) · [location-hiding](location-hiding.md) · [njalla](njalla.md) · [tor-onion-services](tor-onion-services.md)

## Sources

- US DOJ (EDNY), Z-Library charges and domain seizures (16 Nov 2022, archived) — <https://web.archive.org/web/20221117144238/https://www.justice.gov/usao-edny/pr/two-russian-nationals-charged-running-massive-e-book-piracy-website>
- The Record (Nov 2022) — <https://therecord.media/doj-arrests-indicts-russian-nationals-behind-popular-e-book-pirating-site-after-shutdown>
- Njalla FAQ — <https://njal.la/faq/>
