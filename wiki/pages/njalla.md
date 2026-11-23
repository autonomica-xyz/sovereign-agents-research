---
title: "Njalla"
category: compute
status: seed
sources: []
updated: 2026-11-23
---

# Njalla

> A privacy-focused domain and VPS provider that registers domains in its own
> name on the customer's behalf. It has a JSON-RPC API for servers and takes
> crypto including XMR.

## Details

- Domains are held by Njalla as proxy owner, so the customer is not on the
  public record.
- API can create servers (`add-server` with name, type, OS, SSH key).

## How it serves the organism

A domain and a body it can buy and manage by API without a public identity.

## How it fails

Njalla is the legal owner of the domain: it can take it back. No TEE.
Domains remain exposed to registry-level seizure ([dns-seizure](dns-seizure.md)).

## Related

[dns-seizure](dns-seizure.md) · [bitlaunch](bitlaunch.md) · [monero](monero.md)

## Sources

- Njalla API notes — <https://wiki.cyberia.club/hypha/infrastructure_and_operations/njalla>
- Njalla — <https://njal.la/>
