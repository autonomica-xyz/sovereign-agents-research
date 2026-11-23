---
title: "UK AI Security Institute"
category: actor
status: stable
sources: []
updated: 2026-11-23
---

# UK AI Security Institute

> UK government lab that built RepliBench: 86 tasks in 20 families testing
> whether models can get compute, get money, copy their weights and persist.
> The best model tested (Claude 3.7 Sonnet) passed over 50% of tasks at
> pass@10 in 15 of the 20 families.

## Details

- RepliBench splits replication into obtaining resources, exfiltrating
  weights, replicating onto compute and persisting
  ([replibench](replibench.md)).
- Passing KYC failed entirely; robust persistent deployment was also hard.

## How it serves the organism

A public map of which survival skills current models already have.

## How it fails

(As a source) Tests in sandboxes; real-world friction differs.

## Related

[replibench](replibench.md) · [metr](metr.md) · [self-replication](self-replication.md)

## Sources

- AISI — <https://www.aisi.gov.uk/>
- RepliBench — <https://www.aisi.gov.uk/research/replibench-evaluating-the-autonomous-replication-capabilities-of-language-model-agents>
