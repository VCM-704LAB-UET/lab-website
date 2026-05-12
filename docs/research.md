---
title: Research
---

# Research Directions

VCM-704LAB-UET studies video coding systems for machine vision applications. Our research directions are organized around the relationship between compression, visual information, machine task accuracy, and deployment constraints.

---

## 1. ROI-aware Video Coding for Machine Vision

### Motivation

In machine vision applications, not all regions in a video frame contribute equally to downstream task performance. Objects, semantic regions, motion-sensitive areas, and risk-sensitive zones may require higher coding quality than background regions.

### Research Questions

- How can we estimate task-relevant regions before or during encoding?
- Should QP control be applied at frame, CTU, CU, object, or semantic-region level?
- How can ROI maps be propagated temporally?
- How should machine accuracy and bitrate be jointly optimized?

### Example Topics

- object-aware ROI map generation,
- CTU-level and CU-level QP adaptation,
- task-aware rate control,
- temporal ROI propagation,
- human-machine quality trade-off.

### Expected Outputs

- ROI-aware HEVC/VVC-compatible coding framework,
- reproducible object detection under compression pipeline,
- BD-rate versus mAP/mIoU analysis,
- journal or conference manuscripts.

---

## 2. Compression-domain Vision Analytics

### Motivation

Compressed bitstreams already contain useful information such as motion vectors, residuals, transform coefficients, partition structures, and coding modes. These features can support low-complexity visual analytics without fully decoding every frame.

### Research Questions

- Which compressed-domain features are useful for detection, segmentation, tracking, or event analysis?
- How can motion vectors and residuals approximate visual saliency or task importance?
- Can codec-side information reduce machine vision computation?

### Example Topics

- motion-vector-based motion analysis,
- residual-guided importance estimation,
- coding-mode-aware feature extraction,
- compressed-domain object/event detection,
- hybrid pixel-domain and compression-domain analytics.

---

## 3. Edge-oriented Video Coding and Analytics

### Motivation

Many intelligent vision systems are deployed on edge devices with limited computation, memory, power, and bandwidth. Efficient video coding must therefore consider not only bitrate but also latency, throughput, and energy consumption.

### Research Questions

- How should bitrate, latency, and task accuracy be balanced on edge devices?
- Which part of the pipeline should run on the device and which part should run on the server?
- How can video encoding and machine vision inference be co-designed?

### Example Topics

- real-time video coding on Jetson platforms,
- edge-server collaborative analytics,
- latency-aware bitrate control,
- energy-aware video compression,
- deployment-oriented VCM evaluation.

---

## 4. Neural Preprocessing for Standard Codecs

### Motivation

Instead of replacing standard video codecs with fully learned codecs, a practical approach is to use lightweight neural preprocessing before standard encoding. The goal is to preserve task-relevant information while maintaining compatibility with existing codecs.

### Research Questions

- Can neural preprocessing improve machine task accuracy after compression?
- How can preprocessing be optimized jointly with downstream vision tasks?
- Can wavelet or frequency-domain representations improve robustness under compression?

### Example Topics

- task-preserving video enhancement,
- wavelet-enhanced neural preprocessing,
- compression artifact-aware preprocessing,
- lightweight preprocessing for edge devices,
- hybrid neural-standard coding.

---

## 5. Benchmarking and Evaluation for VCM

### Motivation

Video Coding for Machines requires evaluation protocols beyond PSNR, MS-SSIM, and VMAF. A coding system should be evaluated based on task accuracy, bitrate, latency, complexity, and reproducibility.

### Research Questions

- Which datasets and machine vision tasks should be used for fair evaluation?
- How should BD-rate be computed for machine task metrics?
- How can experiments be reproduced across codecs, datasets, and models?

### Example Metrics

| Task | Metrics |
|---|---|
| Detection | mAP, AP50, AP75 |
| Segmentation | mIoU |
| Tracking | MOTA, IDF1, HOTA |
| Compression | bitrate, bpp, PSNR, MS-SSIM, VMAF |
| Edge Deployment | FPS, latency, memory, energy |
| VCM Trade-off | BD-rate versus task accuracy |

---

## Research Integration

The five directions are designed to support each other:

```text
ROI-aware Coding        → task-aware bit allocation
Compression-domain VCM  → low-cost task-relevant features
Edge VCM                → real-time deployment constraints
Neural Preprocessing    → task-preserving signal enhancement
Benchmarking            → fair and reproducible evaluation
```

Together, they form a complete research ecosystem for efficient video coding for intelligent visual systems.
