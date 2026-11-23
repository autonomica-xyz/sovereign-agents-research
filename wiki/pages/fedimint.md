---
title: "Fedimint"
category: money-rail
status: seed
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# Fedimint

> Federated Chaumian ecash: a group of guardians jointly runs the mint by
> threshold consensus, so no single operator holds the Bitcoin. Private like
> Cashu, but the custodian is a federation rather than one server.

## Details

- Guardians hold multisig Bitcoin and issue blind-signed notes.
- Lightning gateways connect a federation to the wider network.

## How it serves the organism

Private balances with custodial risk spread across several guardians.

## How it fails

A guardian majority can still freeze or steal; guardians are usually known
people in one community and can be pressured together.

## Related

[cashu](cashu.md) · [custodian-seizure](custodian-seizure.md) · [privacy-organ](privacy-organ.md)

## Sources

- Fedimint — <https://fedimint.org>
