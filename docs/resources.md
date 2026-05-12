---
title: Tài nguyên
---

# Tài nguyên nghiên cứu

Trang này tổng hợp các tài nguyên nền tảng phục vụ nghiên cứu **Video Coding for Machines (VCM)**, bao gồm nhóm chủ đề đọc paper, dataset, codec, framework thị giác máy, chỉ số đánh giá và checklist tái lập thí nghiệm.

## Nhóm tài liệu cần đọc

| Nhóm chủ đề | Nội dung cần nắm |
|---|---|
| Video Coding Fundamentals | Dự đoán liên ảnh/nội ảnh, transform, quantization, entropy coding, rate-distortion optimization |
| HEVC/VVC | CTU/CU, QP, partitioning, motion compensation, in-loop filtering, reference software |
| Video Coding for Machines | Task-aware compression, collaborative intelligence, feature compression, machine-centric evaluation |
| ROI-aware Coding | ROI map, semantic importance, object-level bit allocation, QP offset control |
| Compression-domain Vision | Motion vector, residual, transform coefficient, coding mode, compressed-domain analytics |
| Edge Video Analytics | Edge-server collaboration, latency, energy, real-time inference, adaptive streaming |
| Evaluation and Benchmarking | BD-rate, mAP, mIoU, tracking metrics, reproducibility protocol |

## Dataset gợi ý

| Dataset | Tác vụ phù hợp | Vai trò trong VCM |
|---|---|---|
| BDD100K | Detection, segmentation, driving scene understanding | Đánh giá VCM trong bối cảnh giao thông và camera hành trình |
| Cityscapes | Semantic segmentation | Phân tích ảnh hưởng nén tới phân đoạn đô thị |
| KITTI | Detection, tracking, autonomous driving | Benchmark cổ điển cho perception trong xe tự hành |
| nuScenes | Detection, tracking, planning-related perception | Phù hợp với nghiên cứu risk-aware hoặc autonomous VCM |
| MOTChallenge | Multi-object tracking | Đánh giá tracking robustness dưới nén |
| DAVIS | Video object segmentation | Đánh giá phân đoạn video và temporal consistency |
| YouTube-VIS | Video instance segmentation | Đánh giá instance-level video understanding |
| COCO subset | Object detection | Baseline nhanh cho detection dưới nén ảnh/video |

## Codec và công cụ xử lý video

| Công cụ | Mục đích sử dụng |
|---|---|
| FFmpeg | Encode/decode, trích xuất frame, phân tích bitrate, chuyển đổi định dạng |
| x264/x265 | Encoder thực dụng cho H.264/H.265, phù hợp baseline nhanh |
| HM | HEVC reference software, phù hợp nghiên cứu chuẩn ở mức chi tiết |
| VTM | VVC reference software, phù hợp nghiên cứu codec thế hệ mới |
| OpenCV | Xử lý ảnh/video, đọc frame, visualization, preprocessing |
| PyAV | Tương tác video trong Python, phù hợp pipeline thí nghiệm |
| NVIDIA Video Codec SDK | Khai thác encode/decode phần cứng trên GPU NVIDIA |

## Framework thị giác máy

| Framework | Vai trò |
|---|---|
| PyTorch | Huấn luyện và đánh giá mô hình học sâu |
| MMDetection | Baseline detection, đo mAP, hỗ trợ nhiều kiến trúc |
| MMSegmentation | Baseline segmentation, đo mIoU |
| Ultralytics YOLO | Baseline detection nhanh, dễ dùng cho sinh viên mới |
| Detectron2 | Detection/segmentation research framework |
| TrackEval | Đánh giá tracking với MOTA, IDF1, HOTA |
| FiftyOne | Quản lý dataset, visualization và phân tích lỗi |

## Chỉ số đánh giá

| Nhóm | Chỉ số | Ý nghĩa |
|---|---|---|
| Compression | bitrate, bpp | Chi phí truyền tải/lưu trữ |
| Signal quality | PSNR, MS-SSIM | Chất lượng tín hiệu hoặc cấu trúc ảnh |
| Perceptual quality | VMAF | Chất lượng cảm nhận của người xem |
| Detection | mAP, AP50, AP75 | Độ chính xác phát hiện đối tượng |
| Segmentation | mIoU, pixel accuracy | Độ chính xác phân đoạn |
| Tracking | MOTA, IDF1, HOTA | Độ ổn định và nhất quán theo thời gian |
| System | FPS, latency, memory, energy | Khả năng triển khai thực tế |
| VCM trade-off | BD-rate versus task metric | Hiệu quả nén xét theo tác vụ máy |

## Checklist tái lập thí nghiệm

Trước khi báo cáo một kết quả, thành viên cần ghi lại tối thiểu:

- tên dataset, phiên bản và split sử dụng,
- cách resize/crop/preprocess dữ liệu,
- codec, encoder, version và tham số mã hoá,
- QP hoặc bitrate ladder,
- mô hình thị giác máy và checkpoint,
- script encode, script evaluate và command chạy,
- random seed nếu có huấn luyện hoặc sampling,
- phần cứng sử dụng,
- bảng kết quả gốc,
- nhận xét về lỗi, ngoại lệ hoặc failure cases.

## Template báo cáo paper

Mỗi paper summary nên có cấu trúc:

```text
1. Citation
2. Problem
3. Main idea
4. Method
5. Experiment setting
6. Main results
7. Strengths
8. Limitations
9. Relation to VCM-704LAB-UET
10. Possible extension
```

## Template báo cáo thí nghiệm

```text
1. Objective
2. Dataset
3. Codec and settings
4. Machine vision model
5. Evaluation metrics
6. Experiment table
7. Observations
8. Failure cases
9. Conclusion
10. Next experiment
```

## Quy tắc lưu trữ tài nguyên

Nhóm không lưu dataset lớn trực tiếp trên GitHub. Repository chỉ nên chứa:

- script tải hoặc chuẩn bị dữ liệu,
- metadata hoặc sample nhỏ,
- cấu hình thí nghiệm,
- mã nguồn,
- bảng kết quả,
- tài liệu hướng dẫn.

Dataset lớn nên được quản lý bằng Google Drive, OneDrive, institutional storage, Hugging Face Datasets, Zenodo hoặc DVC tuỳ từng dự án.