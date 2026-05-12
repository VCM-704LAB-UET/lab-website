---
title: Resources
---

# Resources

This page collects useful resources for students and researchers working on video coding, machine vision, and edge intelligence.

---

## Research Reading List

Recommended categories:

- Video Coding for Machines
- ROI-aware Video Coding
- HEVC / VVC Optimization
- Compression-domain Vision Analytics
- Edge Video Analytics
- Neural Video Preprocessing
- Benchmarking and Evaluation Metrics

---

## Datasets

| Dataset | Typical Tasks | Notes |
|---|---|---|
| BDD100K | Detection, segmentation, driving scene understanding | Useful for autonomous driving video analytics |
| Cityscapes | Segmentation, urban scene understanding | High-quality urban annotations |
| KITTI | Detection, tracking, autonomous driving | Classical benchmark for driving scenes |
| nuScenes | Detection, tracking, planning-related tasks | Multi-sensor autonomous driving dataset |
| MOTChallenge | Multi-object tracking | Suitable for tracking under compression |
| DAVIS | Video object segmentation | Useful for segmentation quality analysis |
| YouTube-VIS | Video instance segmentation | Useful for video-level instance analysis |

---

## Code and Tools

| Tool | Purpose |
|---|---|
| FFmpeg | Video decoding, encoding, transcoding, stream analysis |
| HM | HEVC reference software |
| VTM | VVC reference software |
| x265 | Practical HEVC encoder |
| OpenCV | Video processing and computer vision |
| PyTorch | Deep learning experiments |
| MMDetection | Object detection baseline framework |
| MMSegmentation | Semantic segmentation baseline framework |
| TrackEval | Tracking evaluation |

---

## Evaluation Metrics

| Category | Metrics |
|---|---|
| Compression | bitrate, bpp, PSNR, MS-SSIM, VMAF |
| Detection | mAP, AP50, AP75 |
| Segmentation | mIoU, pixel accuracy |
| Tracking | MOTA, IDF1, HOTA |
| Runtime | FPS, latency, throughput |
| Edge deployment | memory, energy, GPU/CPU usage |

---

## Research Templates

Suggested templates to maintain in the lab workspace:

- paper summary template,
- weekly report template,
- experiment report template,
- project proposal template,
- reproducibility checklist,
- manuscript outline template.

---

## Reproducibility Checklist

Before reporting an experimental result, each member should record:

- dataset version,
- preprocessing script,
- codec and version,
- encoding parameters,
- machine vision model and checkpoint,
- evaluation script,
- random seed,
- hardware information,
- result table,
- analysis notes.
