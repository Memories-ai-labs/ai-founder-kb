# Profiling in PyTorch (Part 1): A Beginner's Guide to torch.profiler
# URL: https://huggingface.co/blog/torch-profiler
# Date: 2026-05-29
# source: Hugging Face Blog
# Authors: Aritra Roy Gosthipaty, Sayak Paul, Sergio Paniego, Rémi Ouazan Reboul, Pedro Cuenca

## Introduction

This post introduces PyTorch profiling through a beginner-friendly lens, starting with the simplest possible operation: a matrix multiplication followed by a bias add. The article is the opening post in a Profiling in PyTorch series that gradually builds profiling skills:

1. **Part 1 (this post):** Learn to read profiler traces using a simple matmul + add operation
2. **Part 2:** Scale up to `nn.Linear` and small MLPs with optimization examples
3. **Part 3:** Apply profiling to Large Language Models with `transformers`

## Key Concepts

- A GPU **kernel** is a program that runs in parallel on many GPU threads
- The CPU **schedules and launches** these kernels
- **Overhead-bound:** CPU spends more time dispatching than GPU computes (small operations)
- **Compute-bound:** GPU is the bottleneck (large operations — usually desired)

## The Matrix Multiplication Example

The example function mimics how weights and biases interact in a neuron:

```python
def fn(x, w, b):
    return torch.add(torch.matmul(x, w), b)
```

### Setting Up torch.profiler

```python
with torch.profiler.profile(
    activities=[
        torch.profiler.ProfilerActivity.CPU,
        torch.profiler.ProfilerActivity.CUDA,
    ],
) as prof:
    for _ in range(5):
        step()
        prof.step()
```

The profiler generates two artifacts:
1. **Profiler Table:** Statistical summary — "What is taking the most time?"
2. **Profiler Trace:** Temporal execution view — "When and Why did operations happen?"

## Key Findings

**64×64 Matrices (overhead-bound):**
- GPU kernel completes in <1% of CPU dispatch time
- First profiler step has ~228 µs cold-start overhead from cuBLAS heuristics
- `cudaDeviceSynchronize` covering tiny GPU work = textbook overhead-bound symptom

**4096×4096 Matrices (compute-bound):**
- CPU and GPU times both in milliseconds
- GPU kernel time dominates — the desired state
- Same kernel timing differs across steps due to GPU clocks, thermals, power management

**torch.compile behavior:**
- Dispatcher-level fusion replaces `torch.add(torch.matmul(x, w), b)` with `aten::addmm`
- Per-call CPU overhead increases (Dynamo → AOTAutograd → Inductor stack tax)
- Amortizes only over models with many operators
- `cudaOccupancyMaxActiveBlocksPerMultiprocessor` before `cudaLaunchKernel` = heavyweight kernel (GEMM, conv)

## Diagnostic Tips

| Signal | Meaning |
|--------|---------|
| `Self CPU time` >> `Self CUDA time` | Overhead-bound — make work bigger or fuse calls |
| `Self CPU time` ≈ `Self CUDA time` | Compute-bound — GPU is bottleneck (usually desired) |
| `cudaOccupancyMaxActiveBlocksPerMultiprocessor` before launch | Heavyweight adaptive kernel |
| Long `cudaDeviceSynchronize` over tiny GPU work | Overhead-bound symptom |
| Same kernel slower across steps | GPU clocks/thermals/power — read traces, not just means |
