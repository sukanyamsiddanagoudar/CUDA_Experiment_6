# Experiment 6 — Results

## GPU and environment

| Item | Recorded value |
|---|---|
| GPU | NVIDIA GeForce RTX 5060 Ti |
| Compute capability | 12.0 |
| CUDA Toolkit | 13.4 (NVCC 13.4.92) |
| Driver reported by `nvidia-smi` | 610.88 |

## Run 1 — Smaller test sizes

- Transpose matrix: 2048 × 2048
- Matrix multiplication: 512 × 512

### Matrix transpose

| Kernel | Time (ms) | Bandwidth (GB/s) | Verification |
|---|---:|---:|---|
| Naive | 0.1786 | 187.85 | PASS |
| Coalesced | 0.0526 | 638.52 | PASS |

Transpose speedup: **3.40×**

### Matrix multiplication

| Measurement | Result |
|---|---:|
| Execution time | 0.1844 ms |
| Performance | 1455.75 GFLOPS |
| Verification | PASS |

## Run 2 — PDF default test sizes

- Transpose matrix: 4096 × 4096
- Matrix multiplication: 1024 × 1024

### Matrix transpose

| Kernel | Time (ms) | Bandwidth (GB/s) | Verification |
|---|---:|---:|---|
| Naive | 0.8209 | 163.49 | PASS |
| Coalesced | 0.4150 | 323.39 | PASS |

Transpose speedup: **1.98×**

### Matrix multiplication

| Measurement | Result |
|---|---:|
| Execution time | 1.3991 ms |
| Performance | 1534.85 GFLOPS |
| Verification | PASS |

## Conclusion

The coalesced transpose was faster than the naive transpose in both recorded runs.
For the 4096 × 4096 transpose, it achieved a 1.98× speedup. The 1024 × 1024
matrix multiplication completed in 1.3991 ms at 1534.85 GFLOPS. All reported
verification checks passed.

## Notes

- These are measurements from the user's actual RTX 5060 Ti system.
- Timings can vary between runs due to GPU load, clock state, temperature, and other
  system activity.
- The screenshots are included as terminal evidence. The source code was not uploaded
  with the screenshots and must be added separately as `main/exp6.cu`.
