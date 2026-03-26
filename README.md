***

<div align="center">

## PackForcing: Short Video Training Suffices for Long Video Sampling and Long Context Inference

[![arXiv](https://img.shields.io/badge/arXiv%20paper-2603.23497-b31b1b.svg)](https://arxiv.org/abs/2603.23497)&nbsp;

</div>

This repository contains the official implementation and benchmark code for the paper:

> [cite_start][**PackForcing: Short Video Training Suffices for Long Video Sampling and Long Context Inference**](https://arxiv.org/abs/2603.23497) [cite: 1]
>
> [cite_start]Xiaofeng Mao, Shaohao Rui, Kaining Ying, Bo Zheng, Chuanhao Li, Mingmin Chi, Kaipeng Zhang [cite: 3]
> 
> Alaya Studio, Shanda AI Research; Fudan University; [cite_start]Shanghai Innovation Institute [cite: 4, 16]

## 💡 Introduction

[cite_start]Autoregressive video diffusion models have demonstrated remarkable progress, yet they remain bottlenecked by intractable linear KV-cache growth, temporal repetition, and compounding errors during long-video generation[cite: 5]. 

[cite_start]To address these challenges, we present **PackForcing**, a unified framework that efficiently manages the generation history through a novel three-partition KV-cache strategy[cite: 6]:

1. [cite_start]**Sink tokens**: Preserve early anchor frames at full resolution to maintain global semantics[cite: 7].
2. [cite_start]**Mid tokens**: Achieve a massive spatiotemporal compression (~32x token reduction) via a dual-branch network fusing progressive 3D convolutions with low-resolution VAE re-encoding[cite: 8]. [cite_start]To bound memory footprint, we introduce a dynamic top-k context selection mechanism[cite: 10].
3. [cite_start]**Recent tokens**: Kept at full resolution to ensure local temporal coherence[cite: 9].

[cite_start]Empowered by this principled hierarchical context compression and a continuous Temporal RoPE Adjustment, PackForcing can generate coherent 2-minute, 832x480 videos at 16 FPS on a single H200 GPU[cite: 10, 11]. [cite_start]It achieves a bounded KV cache of just ~4GB and enables a remarkable 24x temporal extrapolation (from 5s to 120s), operating effectively either zero-shot or trained on merely 5-second clips[cite: 12].

## 📝 TODO List

- [ ] Release inference code
- [ ] Release pre-trained model weights
- [ ] Release VBench evaluation scripts

## 📖 Citation

If you find this project helpful, please consider citing our work:

```bibtex
@misc{mao2026packforcing,
      title={PackForcing: Short Video Training Suffices for Long Video Sampling and Long Context Inference}, 
      author={Xiaofeng Mao and Shaohao Rui and Kaining Ying and Bo Zheng and Chuanhao Li and Mingmin Chi and Kaipeng Zhang},
      year={2026},
      eprint={2603.23497},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2603.23497}, 
}
```

***
