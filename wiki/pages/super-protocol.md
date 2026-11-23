---
title: "Super Protocol"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# Super Protocol

> A confidential AI cloud on TEEs that has pivoted to enterprise and
> government buyers. **Super Swarm**, launched in Feb 2026, runs one trust
> domain of confidential Kubernetes across clouds and bare metal on Intel
> TDX, AMD SEV-SNP and NVIDIA confidential GPUs. A Marketplace offers
> one-click confidential agents, models and data pipelines. Status
> resolved on 23 Nov 2026: live, but sold as an enterprise product, not as
> a permissionless chain.

## Details

- **Company page (read 23 Nov 2026):** "Super Swarm launched in February
  2026. Today it runs confidential AI for healthcare, insurance,
  advertising and AI infrastructure providers". The founder and CEO is
  Nukri Basharuli. The CTO, Denis Bezrukov, leads "confidential
  Kubernetes, TEE-PKI, Deployment Evidence and Gatekeeper".
- **Marketplace flow:** "Nodes are attested, the image is checked against
  its listing and keys are released inside the hardware, all before the
  endpoint goes live." Each deployment produces "Deployment Evidence"
  (image digest, attested node set).
- **Capacity:** Nebius (NVIDIA Blackwell), Gcore with Exxact servers, and
  an install "in your own [Azure] subscription". A Confidential Router
  gives "Top open models through one OpenAI" compatible API.
- **Go-to-market:** sold through Carahsoft, a US public-sector reseller.
  The site has pages on "Sovereign AI", air-gapped deployments and NIST AI
  RMF alignment. Its advisor is Mike Bursell, executive director of the
  Confidential Computing Consortium.
- **History:** earlier material described a Polygon-testnet token plan
  and then a BNB Chain deployment. That post now returns 404, and the
  2026 platform does not lead with a token.

## How it serves the organism

It offers attested, key-releasing deployment across several clouds and
three TEE families (TDX, SEV-SNP, NVIDIA CC). An organism could spread its
body across vendors inside one trust domain, and the Deployment Evidence
format is a useful model for a body proving which image it booted.

## How it fails

- **Contract access:** access is by enterprise contract, so there is no
  wallet-only path for an agent to rent capacity (as far as public pages
  show).
- **Compliance buyers:** the main customers are governments and regulated
  enterprises, so takedown requests will be honoured.
- **Opaque operator set:** the operators are not published.

## Related

[tee-landscape](tee-landscape.md) · [phala-cloud](phala-cloud.md)

## Sources

- Super Protocol — <https://superprotocol.com/>
- Super Protocol FAQ — <https://superprotocol.com/faq>
- About Super Protocol — <https://superprotocol.com/company>
- Super Protocol Marketplace — <https://superprotocol.com/platform/marketplace>
