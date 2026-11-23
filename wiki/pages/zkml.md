---
title: "ZK proofs of computation (zkML, zkVMs)"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# ZK proofs of computation

> Zero-knowledge proofs that a program (or model) ran correctly on hidden
> inputs. General zkVMs (RISC Zero, SP1) and zkML stacks (EZKL) work, but
> proving a large language model's inference is still orders of magnitude
> too slow for real use in 2026; small models and parts of the pipeline are
> provable.

## How it serves the organism

Proves to a counterparty that it did a job without showing its weights or
data; private state transitions for its own records.

## How it fails

Cost and latency; proving does not hide the input from the machine doing
the computation (that needs TEEs or [fhe-inference](fhe-inference.md)).

## Related

[fhe-inference](fhe-inference.md) · [aztec](aztec.md) · [op-inference-confidentiality](op-inference-confidentiality.md)

## Sources

- EZKL — <https://github.com/zkonduit/ezkl>
- RISC Zero — <https://github.com/risc0/risc0>
- SP1 — <https://github.com/succinctlabs/sp1>
