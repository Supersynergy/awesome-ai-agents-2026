# Local model tools

**Checked 13 October 2026** · [Main index](../README.md) · [Model setup guide](MODEL-RUNNING-GUIDE.md)

A serving runtime runs the model. An agent harness supplies the tool loop, context and execution policy. Verify the connection between them on a small task before attempting autonomous work.

## Current serving and desktop tools

| Tool | Useful starting point | Primary documentation |
|---|---|---|
| [Ollama](https://github.com/ollama/ollama) | Local model serving through a CLI and API | [Quickstart](https://docs.ollama.com/quickstart), [model library](https://ollama.com/library) |
| [llama.cpp](https://github.com/ggml-org/llama.cpp) | Portable inference and GGUF tooling | [Upstream guide](https://github.com/ggml-org/llama.cpp#readme) |
| [MLX LM](https://github.com/ml-explore/mlx-lm) | Model inference and fine-tuning with MLX on Apple silicon | [Upstream guide](https://github.com/ml-explore/mlx-lm#readme) |
| [vLLM](https://github.com/vllm-project/vllm) | Serving workloads with batching and accelerator support | [Documentation](https://docs.vllm.ai/en/latest/) |
| [LM Studio](https://lmstudio.ai/) | Desktop model discovery and local API experiments | [Documentation](https://lmstudio.ai/docs) |
| [Jan](https://github.com/janhq/jan) | Desktop local assistant and API workflows | [Documentation](https://jan.ai/docs) |
| [GPT4All](https://github.com/nomic-ai/gpt4all) | Desktop chat and document workflows | [Documentation](https://docs.gpt4all.io/) |
| [LocalAI](https://github.com/mudler/LocalAI) | Self-hosted API compatibility layer | [Documentation](https://localai.io/) |
| [llm-d](https://github.com/llm-d/llm-d) | Kubernetes inference and routing infrastructure | [Documentation](https://llm-d.ai/) |

## Verify the complete agent path

1. Select an exact model artifact supported by the runtime and check its license and integrity.
2. Confirm the loaded model, quantization, context limit and endpoint through the running service.
3. Test chat, streaming and tool calls separately. An API shape described as compatible does not guarantee identical behavior for every client.
4. Connect the harness with an explicit endpoint and model ID; inspect the resolved route and any fallback.
5. Run a small representative task with an external checker and a timeout.
6. Measure the real hardware workload before raising concurrency or context size.

Local operation can reduce network dependence. Privacy depends on endpoints, telemetry, tools and configuration; electricity, hardware, storage and maintenance still have costs. A local chat response alone does not prove safe tool execution.

See the [model setup guide](MODEL-RUNNING-GUIDE.md) for resource planning and acceptance. Current open-source repository fields are in the [metadata snapshot](data/catalog-2026-10-13.json).
