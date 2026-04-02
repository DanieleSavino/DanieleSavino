# Daniele Savino

> *This README was written with AI assistance and manually reviewed. The content accurately reflects my skills and experience — I just didn't want to spend an hour writing about myself.*

3rd year Computer Science student at Sapienza Università di Roma. I like low-level code, parallel systems, and understanding why things are slow.

Currently working on my thesis under [Daniele De Sensi](https://github.com/DanieleDeSensi) — integrating Bine tree collective algorithms into NCCL, targeting the multi-GPU memory hierarchy of modern HPC clusters. Hoping to compete in the SC25 Student Cluster Competition in November 2025.

---

## Skills

| Language / Tool | Level |
|---|---|
| **C** | ⭐⭐⭐⭐ |
| **C++** | ⭐⭐⭐ |
| **CUDA** | ⭐⭐⭐ |
| **MPI** | ⭐⭐⭐ |
| **OpenMP** | ⭐⭐⭐ |
| **Scalasca / Score-P / Cube** | ⭐⭐⭐ |
| **GitHub CI/CD** | ⭐⭐⭐ |
| **perf / PAPI** | ⭐⭐ |
| **NCCL** | ⭐⭐ |
| **Java** | ⭐⭐⭐ |
| **Go** | ⭐⭐ |
| **Python** | ⭐⭐⭐ |
| **Vue.js** | ⭐⭐ |
| **Dart / Flutter** | ⭐⭐ |
| **Rust** | ⭐ |
| **Zig** | ⭐ |

---

## Projects

### [CollAlgo](https://github.com/DanieleSavino/CollAlgo)
Reference implementation of BiNE-based MPI collective algorithms (gather, gatherv, scatter, scatterv, broadcast, allgather, alltoall) in C. Built as a research testbed — clean, instrumented implementations to validate correctness and measure performance before the ideas land in NCCL.

`C` `MPI` `OpenMP`

### [CollBench](https://github.com/DanieleSavino/CollBench)
Lightweight MPI profiling library that instruments individual point-to-point operations with nanosecond-resolution timestamps (start, wait, completion). Records are aggregated across all ranks via `MPI_Gatherv` and exported as JSON. When built without `-DCB_PROFILE` everything compiles away — zero overhead in production.

`C` `MPI`

---

## Thesis

**Implementing Bine Tree Algorithms in NCCL for Multi-GPU Systems**

[NCCL](https://github.com/NVIDIA/nccl) is NVIDIA's standard library for GPU collectives (AllReduce, ReduceScatter, etc.). It is heavily optimized but topology-agnostic at the algorithm level — at scale, inter-node traffic over InfiniBand becomes the main bottleneck.

[Bine trees](https://arxiv.org/pdf/2508.17311) improve communication locality intrinsically: more traffic stays on fast intra-node links (NVLink/NVSwitch), less spills over slow inter-node links. The thesis takes a preliminary flat implementation and evolves it into a hierarchical one that exploits the full memory hierarchy of clusters like Leonardo at CINECA, then benchmarks it against stock NCCL.

---

## What's next

- SC25 Student Cluster Competition — November 2025 (pending confirmation)
- Keep pushing on the NCCL integration and get results worth publishing
