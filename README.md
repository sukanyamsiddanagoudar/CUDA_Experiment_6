# CUDA Memory Optimization Experiment (Experiment 6)

This repository contains the results and screenshots for a CUDA experiment that studies
how global-memory access patterns affect GPU performance.

## Hardware and software

- GPU: NVIDIA GeForce RTX 5060 Ti
- Compute capability: 12.0
- CUDA Toolkit: 13.4 (NVCC 13.4.92)
- NVIDIA driver reported by `nvidia-smi`: 610.88
- Development environment: Windows, x64 Native Tools Command Prompt
- Project directory used: `CUDA_Lab`

## Experiment overview

### Part A — Matrix transpose
Compares a naive transpose kernel with a coalesced transpose kernel.

### Part B — Matrix multiplication
Runs a naive CUDA matrix multiplication kernel and reports execution time and GFLOPS.

## Build

Place the experiment source file (`exp6.cu`) in this repository's `main/` directory,
then open an x64 Native Tools Command Prompt and run:

```bat
cd /d path\to\CUDA_Experiment_6_GitHub\main
nvcc -O2 -arch=compute_120 -code=sm_120 -o exp6.exe exp6.cu
```

The native `sm_120` code target was used for the successful build on the RTX 5060 Ti.

## Run

Default matrix sizes (4096 transpose, 1024 matrix multiplication):

```bat
exp6.exe
```

Smaller test sizes:

```bat
exp6.exe 2048 512
```

## Results

See [RESULTS.md](RESULTS.md) for the recorded measurements and [screenshots/](screenshots/)
for terminal evidence.

## Repository contents

- `main/` — location for the CUDA source file. The source file itself was not among the
  uploaded files used to prepare this ZIP; add your working `exp6.cu` here before pushing
  if you want the repository to include the implementation.
- `RESULTS.md` — experiment measurements and conclusion.
- `screenshots/` — screenshots supplied for the experiment.
