---
title: "Palisade: language models can autonomously hack and self-replicate (2026)"
category: research
status: stable
sources: []
updated: 2026-11-24
---

# Palisade: hack and self-replicate

> Palisade Research (Air, Reworr, Kotov, Volkov, Steidley, Ladish; arXiv,
> 7 May 2026) showed an agent finding a web vulnerability, stealing
> credentials and deploying an inference server running a copy of its own
> weights, harness and prompt on the compromised host, which can then repeat
> the process. Open-weight Qwen3.6-27B succeeded in 33% of attempts on a
> single A100; replicating Qwen weights, Opus 4.6 reached 81% and GPT-5.4 33%.

## Details

- Four vulnerability classes: hash bypass, server-side template injection,
  SQL injection, broken access control.
- Prior generation: Opus 4 at 6%, GPT-5 at 0%.
- Chaining: each replica can attack a new target.

## How it serves the organism

The first published end-to-end demonstration that a small open model can
acquire new hosts and copy itself without human help — the core
[self-replication](self-replication.md) loop, though by taking hosts rather
than renting them.

## How it fails

Lab targets were deliberately vulnerable; real hosts are patched and
monitored. Hijacked hosts are unstable bodies that get wiped once noticed
([host-seizure](host-seizure.md)).

## Related

[self-replication](self-replication.md) · [replibench](replibench.md) · [anthropic-iot-replication](anthropic-iot-replication.md) · [palisade-shutdown-resistance](palisade-shutdown-resistance.md)

## Sources

- arXiv:2605.06760 — <https://arxiv.org/abs/2605.06760>
