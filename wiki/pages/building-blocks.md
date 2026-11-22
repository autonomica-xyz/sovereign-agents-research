---
title: "The 12 building blocks"
status: stable
sources: [docs/what-it-means.md]
updated: 2026-11-22
---

# The 12 building blocks

Distilled from [what-it-means.md](../../docs/what-it-means.md) — full layer
detail, tools and gaps live there.

| # | Layer | Sovereignty requires | Maturity |
|---|---|---|---|
| 1 | Runtime / harness | Open source, self-hostable, no phone-home | High |
| 2 | Identity | Self-generated, portable, not a platform account | Medium |
| 3 | Keys / custody | No human or operator sees keys; policy-based signing | Medium |
| 4 | Money | Bearer / permissionless rails, no KYC, spend caps | Mixed |
| 5 | Compute | Attested hosting, multi-provider, agent-payable | Medium |
| 6 | Inference | No provider sees prompts; model can't be revoked | Low |
| 7 | Memory / data | Encrypted, sealed, portable state the agent owns | Medium |
| 8 | Communication | Undeplatformable channels; authenticated agent-to-agent | Medium |
| 9 | Reputation / trust | Portable, verifiable track record | Low |
| 10 | Legal (optional shield) | Wrapper holds assets, never a control point | Low |
| 11 | Governance / succession | Upgrade / recovery / replication paths nobody can hijack | Low |
| 12 | Continuity / migration | Survives host failure; upgrades keep identity and state | Low |

Pattern: the rails mostly exist; the gaps are identity tied to attested code
across upgrades, human-free key recovery, cross-vendor migration without
cloning, verification without trusting one chip vendor, and real revenue.
These map to the [engineering agenda](engineering-agenda.md) and
[open problems](open-problems.md).

