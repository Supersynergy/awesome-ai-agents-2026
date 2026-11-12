# Running a model for an agent

**Checked 13 October 2026** · [Local model tools](LOCAL-LLM-TOOLS.md) · [Harness research](HARNESS-RESEARCH.md)

Choose an exact model artifact, establish a working runtime, then verify the harness connection. Model names and tags change quickly: use the [publisher's model card](https://huggingface.co/models) or [Ollama library](https://ollama.com/library) to resolve the current artifact.

## Record before downloading

| Field | Why it matters |
|---|---|
| Publisher, model ID and immutable revision | Identifies the artifact actually tested |
| Artifact format and quantization | Determines runtime compatibility and weight storage |
| License and usage conditions | Establishes what the artifact permits |
| File size and checksum | Supports storage planning and integrity verification |
| Supported context and tool-call format | Constrains the workload and harness connection |
| Runtime version and acceleration backend | Makes behavior and measurements reproducible |

A model card is source information. It does not prove that the file on disk matches the card or that the running service loaded it.

## Plan memory and storage

Raw weight storage is approximately parameter count × bits per weight ÷ 8. This is an estimate before quantization metadata, runtime buffers and other allocations. Context state, batch size, KV-cache format and concurrency add memory requirements.

Measure the exact workload on the actual machine. Keep capacity for the operating system and other jobs. On unified-memory machines, CPU, GPU and shared allocations must fit together; process RSS alone may miss part of that footprint. Record memory pressure, swap activity and peak use while a representative request runs.

Reserve storage for both the downloaded artifact and any conversion output. Preserve the verified original until the converted artifact has passed loading and inference checks. Avoid downloading a second copy when an existing verified artifact is usable.

## Verify in stages

1. Artifact: check provenance, revision, integrity, format and license.
2. Runtime: load the exact file, confirm acceleration and complete a deterministic smoke request.
3. API: exercise a normal response, streaming, cancellation and malformed input.
4. Tools: verify tool-call parsing and a harmless tool round trip through the chosen harness.
5. Task: run a representative bounded task and its external checker.
6. Recovery: stop and restart the runtime; check interrupted-task behavior and resource cleanup.

Keep artifact, runtime and task evidence separate. A successful download does not establish inference, and inference does not establish agent task completion.

## Measure before changing settings

| Measurement | Report with it |
|---|---|
| First response and completed response time | Input length, output length, cold or warm state |
| Output throughput | Sampling settings, concurrency and measurement interval |
| Memory footprint | Context length, batch size, cache format and other active jobs |
| Task success | Exact harness, model route, verifier and repeated trials |
| Total effort | Failures, retries, checking, review and human intervention |

Change one variable at a time while holding the task and acceptance fixed. Lower quantization, longer context or more workers should earn their place through observed results.

Use current upstream instructions for [Ollama](https://docs.ollama.com/quickstart), [llama.cpp](https://github.com/ggml-org/llama.cpp), [MLX LM](https://github.com/ml-explore/mlx-lm), [vLLM](https://docs.vllm.ai/en/latest/) or [LM Studio](https://lmstudio.ai/docs). This guide intentionally avoids guessed model tags, hardware speed promises and stale command examples.
