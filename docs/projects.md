---
title: Dự án
---

# Dự án nghiên cứu

Trang này mô tả danh mục dự án của VCM-704LAB-UET. Mỗi dự án được thiết kế như một đơn vị nghiên cứu có mục tiêu rõ ràng, baseline có khả năng tái lập, phương pháp đề xuất, giao thức đánh giá và đầu ra học thuật.

## Danh mục dự án trọng tâm

| Mã dự án | Tên dự án | Mục tiêu | Trạng thái |
|---|---|---|---|
| VCM-ROI | ROI-aware Video Coding for Machine Vision | Phân bổ bitrate theo vùng quan trọng cho detection/segmentation/tracking | Đang khởi động |
| VCM-CDV | Compression-domain Vision Analytics | Khai thác motion vector, residual và coding information cho phân tích chi phí thấp | Đang khởi động |
| VCM-EDGE | Edge-oriented Video Coding and Analytics | Tối ưu pipeline mã hoá và AI vision trên thiết bị biên | Đang khởi động |
| VCM-NPP | Neural Preprocessing for Standard Codecs | Tiền xử lý bằng học sâu trước HEVC/VVC để bảo toàn thông tin tác vụ | Lập kế hoạch |
| VCM-BENCH | Benchmarking Protocol for VCM | Xây dựng bộ đánh giá tái lập cho video coding for machines | Lập kế hoạch |

---

## VCM-ROI: ROI-aware Video Coding for Machine Vision

### Mục tiêu

Dự án phát triển pipeline mã hoá video trong đó các vùng quan trọng đối với tác vụ máy được ưu tiên bitrate. Đây là hướng phù hợp để tạo baseline và bài báo đầu tiên vì có thể triển khai theo lộ trình rõ ràng: detector/ground-truth ROI → ROI map → QP map → encode → evaluate task accuracy.

### Thành phần kỹ thuật

- Sinh ROI map từ ground truth, detector hoặc tracker.
- Chuyển ROI map thành QP offset map ở mức CTU/CU.
- Tích hợp với encoder HEVC/VVC hoặc encoder thực dụng.
- Đánh giá trên detection, segmentation hoặc tracking.
- Phân tích trade-off giữa bitrate, task accuracy và perceptual quality.

### Đầu ra

| Giai đoạn | Sản phẩm |
|---|---|
| Baseline | Encode cùng một dataset ở nhiều QP và đo mAP/mIoU |
| Prototype | ROI-based QP adaptation |
| Evaluation | BD-rate versus task accuracy |
| Publication | Workshop/conference paper về task-aware ROI coding |

---

## VCM-CDV: Compression-domain Vision Analytics

### Mục tiêu

Dự án nghiên cứu khả năng sử dụng thông tin miền nén để hỗ trợ hoặc thay thế một phần xử lý pixel-domain. Hướng này phù hợp với các bài toán cần giảm chi phí tính toán, ví dụ camera thông minh hoặc phân tích video thời gian thực.

### Thành phần kỹ thuật

- Trích xuất motion vectors, residuals, coding modes và partition maps.
- Phân tích tương quan giữa đặc trưng miền nén và vùng quan trọng cho tác vụ.
- Xây dựng mô hình nhẹ sử dụng compressed-domain features.
- So sánh chi phí tính toán với pipeline pixel-domain.

### Đầu ra

| Giai đoạn | Sản phẩm |
|---|---|
| Tooling | Script extract motion/residual/coding features |
| Analysis | Báo cáo tương quan compression-domain features với task errors |
| Prototype | Lightweight compressed-domain analytics module |
| Publication | Paper về low-complexity VCM hoặc compressed-domain vision |

---

## VCM-EDGE: Edge-oriented Video Coding and Analytics

### Mục tiêu

Dự án tập trung vào bối cảnh triển khai thực tế trên thiết bị biên, nơi hệ thống phải xử lý video dưới ràng buộc về latency, memory, energy và bandwidth. Đây là hướng có tính ứng dụng mạnh, phù hợp với robot, camera thông minh, thiết bị Jetson và edge-server analytics.

### Thành phần kỹ thuật

- Xây dựng pipeline capture/decode/preprocess/encode/infer.
- Profiling CPU, GPU, RAM, FPS và latency.
- Điều chỉnh bitrate hoặc QP theo phản hồi tác vụ.
- So sánh xử lý local, edge-server và hybrid.

### Đầu ra

| Giai đoạn | Sản phẩm |
|---|---|
| System baseline | Pipeline chạy được trên edge device |
| Profiling | Bảng latency, FPS, memory, energy |
| Adaptive method | Điều khiển mã hoá theo task feedback |
| Demo | Real-time edge VCM demonstration |

---

## VCM-NPP: Neural Preprocessing for Standard Codecs

### Mục tiêu

Dự án nghiên cứu cách dùng mạng học sâu để tiền xử lý video trước khi đưa vào codec chuẩn. Mục tiêu là tăng khả năng giữ lại thông tin có ích cho mô hình thị giác máy mà vẫn không phá vỡ tính tương thích với hệ sinh thái codec hiện có.

### Thành phần kỹ thuật

- Thiết kế neural preprocessing network nhẹ.
- Tối ưu theo task loss hoặc hybrid perceptual-task loss.
- Kết hợp wavelet/frequency-domain module nếu phù hợp.
- Đánh giá ảnh hưởng đến bitrate và task accuracy.

### Đầu ra

| Giai đoạn | Sản phẩm |
|---|---|
| Baseline | Preprocess + encode + task evaluation |
| Method | Task-preserving preprocessing module |
| Analysis | Ablation về loss, architecture và bitrate |
| Publication | Paper về hybrid neural-standard video coding for machines |

---

## VCM-BENCH: Benchmarking Protocol for VCM

### Mục tiêu

Dự án xây dựng bộ giao thức đánh giá thống nhất cho toàn nhóm. Đây là nền tảng quan trọng để các dự án khác có thể so sánh công bằng và tái lập.

### Thành phần kỹ thuật

- Chọn dataset và task phù hợp.
- Thiết kế encoding ladder.
- Chuẩn hoá script encode/evaluate.
- Tạo bảng kết quả baseline.
- Xây dựng reproducibility checklist.

### Đầu ra

| Giai đoạn | Sản phẩm |
|---|---|
| Protocol | Quy trình đánh giá codec và task model |
| Scripts | Encode/evaluate/reproduce scripts |
| Baselines | Bảng kết quả HEVC/VVC/H.264 trên các task |
| Release | Public benchmark documentation |

---

## Quy trình quản lý dự án

Mỗi dự án của nhóm cần tuân theo cấu trúc sau:

```text
project-name/
├── README.md
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

## Chuẩn đầu ra cho một task nghiên cứu

Một task chỉ được xem là hoàn thành khi có đủ:

- mô tả bài toán,
- mã nguồn hoặc tài liệu liên quan,
- hướng dẫn chạy,
- log hoặc kết quả thực nghiệm,
- phân tích ngắn về ý nghĩa kết quả,
- liên kết tới issue hoặc pull request,
- vị trí lưu output trong repository.

## Mã hoá task

| Nhóm task | Quy ước |
|---|---|
| ROI-aware coding | ROI-001, ROI-002, ... |
| Compression-domain vision | CDV-001, CDV-002, ... |
| Edge VCM | EDGE-001, EDGE-002, ... |
| Neural preprocessing | NPP-001, NPP-002, ... |
| Benchmarking | BENCH-001, BENCH-002, ... |
| Paper writing | PAPER-001, PAPER-002, ... |

## Nguyên tắc ưu tiên

Trong giai đoạn đầu, nhóm ưu tiên các dự án có thể tạo ra baseline nhanh, có dữ liệu rõ, có khả năng tái lập và có thể mở rộng thành bài báo. Do đó, thứ tự ưu tiên đề xuất là:

1. VCM-BENCH để có nền tảng đánh giá.
2. VCM-ROI để có phương pháp đầu tiên.
3. VCM-CDV để tạo hướng mới có chiều sâu học thuật.
4. VCM-EDGE để tăng tính triển khai và ứng dụng.
5. VCM-NPP để mở rộng sang hướng hybrid neural-standard coding.