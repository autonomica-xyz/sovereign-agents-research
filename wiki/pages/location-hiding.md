---
title: "Location hiding"
category: concept
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Location hiding

> If nobody can find the organism's hosts, nobody can seize or unplug them.
> Location hiding covers onion routing for services, paying for hosts without
> linking payments, and reaching peers by key instead of by IP or DNS name.

## Details

- **Onion services:** [tor-onion-services](tor-onion-services.md) with
  Onionbalance (one .onion across several backends) and Arti 2.8 (vanguards,
  proof-of-work anti-DoS); I2P multihoming.
- **Dial by key:** [iroh](iroh.md) endpoints are public keys; relays forward
  encrypted traffic. [nostr](nostr.md) identities are keys; relays are many.
- **Buy hosts unlinkably:** [monero](monero.md), [cashu](cashu.md) or
  Lightning to a no-KYC host ([bitlaunch](bitlaunch.md), [njalla](njalla.md),
  [hosting-1984](hosting-1984.md)); order over Tor where the API allows.
- **No DNS:** avoid [dns-seizure](dns-seizure.md) by being reachable by key.

## How it serves the organism

A hidden body cannot be raided, and a hidden payment trail does not lead from
one body to the next.

## How it fails

- Default relays (n0's iroh relays, popular Nostr relays) see connection
  metadata ([op-metadata-privacy](op-metadata-privacy.md)).
- Onion services can be deanonymised by traffic analysis and server
  misconfiguration.
- TEEs are not hidden: attestation reveals hardware identity (PPID, chip ID)
  to whoever verifies it.

## Related

[privacy-organ](privacy-organ.md) · [not-get-killed](not-get-killed.md) · [op-metadata-privacy](op-metadata-privacy.md)

## Sources

- Onionbalance — <https://onionservices.torproject.org/apps/base/onionbalance/>
- Arti 2.8.0 release — <https://blog.torproject.org/arti_2_8_0_released/>
- iroh — <https://github.com/n0-computer/iroh>
