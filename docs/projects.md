---
title: Projects
---

# Projects

This page summarizes active and planned research projects of VCM-704LAB-UET.

!!! note
    Project names, leaders, members, and repository links should be updated as the team grows.

---

## Active Projects

| Project | Direction | Description | Status |
|---|---|---|---|
| ROI-aware VCM | ROI-aware Video Coding | Task-aware bit allocation for machine vision under compression | Active |
| Compression-domain VCM | Compression-domain Vision | Use motion vectors, residuals, and coding information for low-complexity analytics | Active |
| Edge VCM | Edge-oriented Coding | Real-time coding and machine vision pipeline on edge devices | Active |
| Neural Preprocessing VCM | Neural Preprocessing | Task-preserving preprocessing before HEVC/VVC encoding | Planning |
| VCM Benchmark | Benchmarking | Reproducible evaluation protocol for video coding for machines | Planning |

---

## Project Template

Each project should include:

- clear problem statement,
- related work summary,
- baseline method,
- proposed method,
- dataset and evaluation protocol,
- reproducible source code,
- experimental results,
- manuscript or technical report.

---

## Recommended Repository Structure

```text
project-name/
├── README.md
├── LICENSE
├── requirements.txt or environment.yml
├── docs/
│   ├── problem.md
│   ├── related_work.md
│   ├── method.md
│   └── experiment_protocol.md
├── src/
│   ├── data/
│   ├── encoding/
│   ├── models/
│   ├── evaluation/
│   └── utils/
├── configs/
├── scripts/
├── experiments/
├── results/
└── papers/
```

---

## Project Management Rule

Every project should be managed using GitHub Issues and Milestones.

Each task should specify:

- objective,
- assignee,
- deadline,
- expected output,
- related paper or baseline,
- output location,
- review status.

---

## Suggested Task Codes

| Code | Meaning |
|---|---|
| ROI-xxx | ROI-aware video coding |
| CDV-xxx | Compression-domain vision |
| EDGE-xxx | Edge-oriented VCM |
| NPP-xxx | Neural preprocessing |
| BENCH-xxx | Benchmarking and evaluation |
| PAPER-xxx | Paper writing |
| ADMIN-xxx | Lab administration |

---

## Example Task

```markdown
# [ROI-001] Survey ROI-aware Video Coding for Machine Vision

## Objective
Survey recent works on ROI-aware video coding for machine vision, focusing on HEVC/VVC-compatible methods.

## Expected Deliverables
- Summary table of at least 20 papers
- Taxonomy of ROI-aware VCM methods
- 5-page technical report
- Weekly meeting slide

## Deadline
YYYY-MM-DD

## Assignee
@member-name
```
