# Latest Models 2025 - Comprehensive Local Running Guide

> **Historical guide:** This document is retained for older local-running examples. It is not the current model inventory. Use the dated [current README](README.md) and verify model names in the upstream runtime before downloading anything.

A complete guide to running the latest AI models locally, including hardware requirements, quantization options, and optimization tips.

## Table of Contents

- [November 2025 Models](#november-2025-models)
- [Model Sizes and Requirements](#model-sizes-and-requirements)
- [Quantization Guide](#quantization-guide)
- [Hardware Recommendations](#hardware-recommendations)
- [Performance Benchmarks](#performance-benchmarks)
- [Memory Optimization](#memory-optimization)
- [Multi-Model Loading](#multi-model-loading)

---

## November 2025 Models

### Llama 4 Family (Meta)

Meta's latest Llama 4 introduces native multimodal capabilities and improved reasoning.

| Variant | Parameters | Base RAM | Quantized (Q4) | Best For |
|---------|------------|----------|----------------|----------|
| Llama 4 Scout | 8B | 16GB | 6GB | Efficient tasks, edge deployment |
| Llama 4 Maverick | 70B | 140GB | 45GB | Complex reasoning, production |
| Llama 4 Pioneer | 405B | 810GB | 250GB | Research, multi-GPU setups |

**Key Features:**
- Native image understanding (no adapter needed)
- Improved instruction following
- Better multilingual support
- Enhanced code generation

**Running Locally:**
```bash
# Scout variant (runs on most hardware)
ollama pull llama4:scout

# Maverick variant (needs significant RAM/VRAM)
ollama pull llama4:maverick-q4

# With vision
ollama run llama4:scout "Describe this image" -i ./image.jpg
```

---

### Qwen3 Series (Alibaba)

Alibaba's Qwen3 represents a major architecture upgrade with specialized variants.

| Variant | Parameters | Base RAM | Quantized (Q4) | Best For |
|---------|------------|----------|----------------|----------|
| Qwen3 Base | 7B | 14GB | 5GB | General tasks |
| Qwen3 | 14B | 28GB | 10GB | Balanced performance |
| Qwen3 | 32B | 64GB | 20GB | Advanced reasoning |
| Qwen3-Coder | 480B | 960GB | 300GB | Enterprise coding |
| Qwen3-Omni | Various | Various | Various | Multimodal |

**Key Features:**
- Qwen3-Next architecture improvements
- Omni-modal capabilities
- Massive context windows (128K+)
- Specialized coder variant

**Running Locally:**
```bash
# Standard Qwen3
ollama pull qwen3:14b

# Coder variant
ollama pull qwen3-coder:14b

# For agentic coding workflows
ollama run qwen3-coder:14b --context 32768
```

---

### DeepSeek V3/R1 (DeepSeek)

DeepSeek's latest models focus on efficiency and reasoning capabilities.

| Variant | Parameters | Base RAM | Quantized (Q4) | Best For |
|---------|------------|----------|----------------|----------|
| DeepSeek V3 | 67B | 134GB | 42GB | General purpose |
| DeepSeek V3.2-Exp | 67B | 134GB | 42GB | Experimental features |
| DeepSeek R1 | Various | Various | Various | Chain-of-thought reasoning |

**Key Features:**
- Mixture-of-Experts architecture
- Excellent reasoning capabilities
- Cost-effective inference
- Strong math/code performance

**Running Locally:**
```bash
# Latest DeepSeek
ollama pull deepseek-v3:latest

# Reasoning model
ollama pull deepseek-r1:latest

# With higher context
ollama run deepseek-v3:latest --context 65536
```

---

### Other Notable Releases

#### GPT-OSS (OpenAI)
OpenAI's first open-source model release.

```bash
ollama pull gpt-oss:latest
```

#### Phi 4 (Microsoft)
Compact but powerful models for edge deployment.

```bash
ollama pull phi4:3b
ollama pull phi4:14b
```

#### Grok 3/4 (xAI)
Latest iterations with improved capabilities.

```bash
ollama pull grok3:latest
ollama pull grok4:latest
```

---

## Quantization Guide

Quantization reduces model size and memory requirements at the cost of some quality.

### Quantization Levels

| Level | Bits | Quality | Size Reduction | Memory Savings | Use Case |
|-------|------|---------|----------------|----------------|----------|
| F16 | 16 | 100% | Baseline | None | Research, max quality |
| Q8_0 | 8 | 99% | 50% | 50% | High quality, more RAM |
| Q6_K | 6 | 97% | 62% | 62% | Balanced quality/size |
| Q5_K_M | 5 | 95% | 69% | 69% | Good balance |
| Q4_K_M | 4 | 90% | 75% | 75% | Most popular |
| Q4_K_S | 4 | 88% | 75% | 75% | Smaller Q4 variant |
| Q3_K_M | 3 | 80% | 81% | 81% | Low memory systems |
| Q2_K | 2 | 70% | 87% | 87% | Minimal RAM, low quality |

### Choosing the Right Quantization

**For Most Users: Q4_K_M**
- Best balance of quality and performance
- Works well on consumer hardware
- Noticeable but acceptable quality loss

**For Quality-Critical Tasks: Q5_K_M or Q6_K**
- Better output quality
- Needs more RAM
- Good for production systems

**For Limited Hardware: Q3_K_M or Q2_K**
- Runs on low-RAM systems
- Quality degradation noticeable
- Good for testing and development

### Quantization Commands

```bash
# Pull specific quantization
ollama pull llama4:scout-q4_K_M
ollama pull llama4:scout-q5_K_M
ollama pull llama4:scout-q8_0

# List available quantizations
ollama show llama4:scout --modelfile
```

---

## Hardware Recommendations

### CPU-Only Systems

| Model Size | Min RAM | Recommended RAM | Performance |
|------------|---------|-----------------|-------------|
| 3B (Q4) | 4GB | 8GB | Good |
| 7B (Q4) | 6GB | 16GB | Acceptable |
| 14B (Q4) | 12GB | 24GB | Slow |
| 32B (Q4) | 24GB | 48GB | Very Slow |

**Tips:**
- Enable memory mapping
- Use lower quantization
- Reduce context window
- Consider swap space

### NVIDIA GPU Systems

| GPU | VRAM | Max Model (Q4) | Performance |
|-----|------|----------------|-------------|
| RTX 3060 | 12GB | 13B | Good |
| RTX 3080 | 10GB | 7B | Excellent |
| RTX 3090 | 24GB | 30B | Excellent |
| RTX 4070 | 12GB | 13B | Excellent |
| RTX 4080 | 16GB | 20B | Excellent |
| RTX 4090 | 24GB | 30B | Outstanding |
| A100 | 40/80GB | 70B+ | Professional |

### Apple Silicon

| Chip | Unified Memory | Max Model (Q4) | Performance |
|------|----------------|----------------|-------------|
| M1 | 8GB | 7B | Good |
| M1 | 16GB | 13B | Good |
| M1 Pro | 32GB | 30B | Very Good |
| M1 Max | 64GB | 70B | Excellent |
| M2 | 24GB | 20B | Good |
| M2 Pro | 32GB | 30B | Very Good |
| M2 Max | 96GB | 70B+ | Excellent |
| M3 | 24GB | 20B | Very Good |
| M3 Pro | 36GB | 40B | Excellent |
| M3 Max | 128GB | 100B+ | Outstanding |
| M4 Pro | 48GB | 50B | Outstanding |
| M4 Max | 128GB | 100B+ | Outstanding |

**Apple Silicon Tips:**
- Unified memory allows larger models
- Metal acceleration is automatic
- Performance improves with newer chips
- Memory bandwidth matters

### Multi-GPU Configurations

| Configuration | Total VRAM | Max Model (Q4) | Notes |
|---------------|------------|----------------|-------|
| 2x RTX 4090 | 48GB | 70B | Great for production |
| 4x RTX 4090 | 96GB | 100B+ | Enterprise setup |
| 2x A100 80GB | 160GB | 200B+ | Research grade |
| 8x H100 80GB | 640GB | 400B+ | Maximum scale |

---

## Performance Benchmarks

### Tokens per Second (November 2025)

#### 7B Models (Q4_K_M)

| Hardware | Llama 4 Scout | Qwen3 7B | Mistral 7B |
|----------|---------------|----------|------------|
| RTX 4090 | 120 t/s | 115 t/s | 125 t/s |
| RTX 4080 | 90 t/s | 85 t/s | 95 t/s |
| RTX 3090 | 80 t/s | 75 t/s | 85 t/s |
| M3 Max | 70 t/s | 65 t/s | 75 t/s |
| M2 Max | 50 t/s | 45 t/s | 55 t/s |
| CPU (32 core) | 15 t/s | 12 t/s | 18 t/s |

#### 14B Models (Q4_K_M)

| Hardware | Qwen3 14B | Phi 4 14B |
|----------|-----------|-----------|
| RTX 4090 | 75 t/s | 80 t/s |
| RTX 4080 | 55 t/s | 60 t/s |
| M3 Max | 45 t/s | 50 t/s |
| M2 Max | 30 t/s | 35 t/s |

#### 70B Models (Q4_K_M)

| Hardware | Llama 4 Maverick | DeepSeek V3 |
|----------|------------------|-------------|
| RTX 4090 | 20 t/s | 18 t/s |
| 2x RTX 4090 | 35 t/s | 32 t/s |
| M3 Max 128GB | 25 t/s | 22 t/s |

---

## Memory Optimization

### Context Window Optimization

Larger context windows use more memory:

| Context Size | Additional RAM (7B) | Additional RAM (70B) |
|--------------|---------------------|----------------------|
| 2K tokens | Baseline | Baseline |
| 4K tokens | +200MB | +2GB |
| 8K tokens | +400MB | +4GB |
| 16K tokens | +800MB | +8GB |
| 32K tokens | +1.6GB | +16GB |
| 128K tokens | +6.4GB | +64GB |

**Optimization Tips:**
```bash
# Set appropriate context for your task
ollama run llama4:scout --context 4096  # Short conversations
ollama run llama4:scout --context 16384 # Longer documents
ollama run llama4:scout --context 65536 # RAG applications
```

### Batch Size Optimization

```bash
# For throughput (more memory)
ollama run model --batch-size 512

# For low memory (slower)
ollama run model --batch-size 64
```

### Memory Mapping

Enable for large models on systems with less RAM:
```bash
# In modelfile
FROM llama4:scout
PARAMETER num_gpu 0
PARAMETER mmap true
```

---

## Multi-Model Loading

### Running Multiple Models

```bash
# Terminal 1: Main reasoning model
ollama run llama4:maverick

# Terminal 2: Code model
ollama run qwen3-coder:14b

# Terminal 3: Vision model
ollama run llava:34b
```

### Memory Considerations

Total RAM needed = Sum of all loaded models + OS overhead

**Example Setup (64GB RAM):**
- Llama 4 Scout Q4: 6GB
- Qwen3-Coder 14B Q4: 10GB
- Embedding model: 2GB
- OS and apps: 16GB
- Total: 34GB (leaves headroom)

### Model Switching Strategies

**Hot Loading (Keep in Memory):**
- Fast switching
- More memory required
- Good for frequently used models

**Cold Loading (Unload Between Uses):**
- Lower memory usage
- Loading delay
- Good for occasional use

---

## Best Practices

### For Agents

1. **Use appropriate model sizes** - Bigger isn't always better
2. **Match quantization to hardware** - Q4 for most, Q5+ for quality
3. **Set context appropriately** - Don't waste memory on unused context
4. **Consider specialized models** - Coder for code, etc.

### For Production

1. **Benchmark thoroughly** - Test with real workloads
2. **Monitor memory usage** - Avoid OOM situations
3. **Plan for scaling** - Consider multi-GPU
4. **Use consistent quantization** - For reproducible results

### For Development

1. **Start small** - Test with 7B models first
2. **Iterate quickly** - Use lower quantization for testing
3. **Profile performance** - Understand bottlenecks
4. **Document requirements** - Track what works

---

## Troubleshooting

### Out of Memory

```bash
# Reduce context window
ollama run model --context 2048

# Use smaller quantization
ollama pull model-q3_K_M

# Enable swap (Linux)
sudo swapon /swapfile
```

### Slow Performance

```bash
# Check GPU utilization
nvidia-smi

# Ensure GPU is being used
ollama run model --verbose

# Reduce batch size
ollama run model --batch-size 128
```

### Model Won't Load

```bash
# Check available memory
free -h

# Clear Ollama cache
rm -rf ~/.ollama/models

# Re-pull model
ollama pull model
```

---

## Resources

- [Ollama Model Library](https://ollama.com/library)
- [Hugging Face Model Hub](https://huggingface.co/models)
- [GGUF Quantization Guide](https://github.com/ggerganov/llama.cpp/tree/master/examples/quantize)
- [r/LocalLLaMA](https://reddit.com/r/LocalLLaMA)

---

Last Updated: November 2025
