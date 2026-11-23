---
title: "Open problem: metadata privacy"
category: open-problem
status: seed
sources: [wiki/pages/privacy-organ.md]
updated: 2026-11-23
---

# Open problem: metadata privacy

> Even when content is encrypted, who the organism talks to, pays and rents
> from, and when, maps its bodies, family and suppliers. No stack in 2026
> hides payments, network location and supplier relationships at once.

## Details

- Payments: transparent chains expose balances and links
  ([public-balance-exposure](public-balance-exposure.md)); ecash hides
  amounts from the mint but the mint sees redemption timing; Lightning hides
  some payer data but channels are public.
- Network: iroh and Nostr relays see IPs unless routed through Tor or a
  mixnet ([location-hiding](location-hiding.md), [tor-onion-services](tor-onion-services.md)).
- Suppliers: every host knows which IP it rented to which payment.
- Inference: prompts reveal intentions to providers
  ([op-inference-confidentiality](op-inference-confidentiality.md)).

## How it serves the organism

Privacy is a survival organ: unseen bodies are not seized
([privacy-organ](privacy-organ.md)).

## How it fails

Correlation across layers (payment time plus server start plus relay IP)
deanonymises even when each layer is private alone.

## Related

[privacy-organ](privacy-organ.md) · [location-hiding](location-hiding.md) · [cashu](cashu.md) · [monero](monero.md) · [open-problems](open-problems.md)

## Sources

- Wiki privacy hub — [privacy-organ](privacy-organ.md)
- Tor onion services — <https://community.torproject.org/onion-services/>
