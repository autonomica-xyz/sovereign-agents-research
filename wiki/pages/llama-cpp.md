---
title: "llama.cpp (and its RPC backend)"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# llama.cpp

> The C/C++ inference engine (Georgi Gerganov, 2023) that made LLMs run on
> CPUs, phones and small GPUs, and defined the GGUF quantized format. Its RPC
> backend lets one machine offload layers to `rpc-server` processes on other
> machines.

## Details

- Runs on almost anything: x86, ARM, Apple Silicon, CUDA, Vulkan, ROCm.
- GGUF quantization from ~1.5 to 8 bits per weight
  ([local-models-quantization](local-models-quantization.md)).
- RPC mode has no authentication or encryption: only for trusted networks.
- The engine behind Ollama and many agent runtimes; Anthropic's IoT
  replication tests used small-device inference of this kind
  ([anthropic-iot-replication](anthropic-iot-replication.md)).

## How it serves the organism

The universal "mind runtime": if a device can boot, it can probably think.

## How it fails

Small devices mean small models; RPC is insecure over the internet.

## Related

[local-models-quantization](local-models-quantization.md) · [exo](exo.md) · [distributed-llama](distributed-llama.md)

## Sources

- llama.cpp — <https://github.com/ggml-org/llama.cpp>
- llama.cpp RPC — <https://github.com/ggml-org/llama.cpp/tree/master/tools/rpc>
