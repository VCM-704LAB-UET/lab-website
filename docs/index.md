---
title: Trang chủ
hide:
  - toc
---

<section class="vcm-landing" markdown>

<div class="vcm-hero-pro" markdown>
<div class="vcm-hero-left" markdown>

<div class="vcm-eyebrow">VCM-704LAB-UET · Research Group</div>

# Video Coding for Machines

## Mã hoá video hướng tác vụ cho các hệ thống thị giác máy, thiết bị biên và phân tích video thông minh.

VCM-704LAB-UET nghiên cứu các phương pháp **mã hoá video thế hệ mới** trong đó tín hiệu video không chỉ được tối ưu cho chất lượng cảm nhận của con người, mà còn được tối ưu cho hiệu năng của các mô hình thị giác máy như phát hiện đối tượng, phân đoạn, theo vết, nhận dạng sự kiện và hệ thống tự hành.

<div class="vcm-actions" markdown>
[Hướng nghiên cứu](research.md){ .md-button .md-button--primary }
[Dự án đang triển khai](projects.md){ .md-button .vcm-button-secondary }
</div>

</div>

<div class="vcm-hero-right" markdown>
<div class="vcm-system-card" markdown>

<div class="vcm-system-title">Task-aware Video Coding Pipeline</div>

<div class="vcm-pipeline" markdown>
<div>Video Stream</div>
<span>→</span>
<div>Semantic / ROI Analysis</div>
<span>→</span>
<div>Codec Control</div>
<span>→</span>
<div>Machine Vision Task</div>
</div>

<div class="vcm-mini-metrics" markdown>
<div><strong>Bitrate</strong><span>↓</span></div>
<div><strong>Accuracy</strong><span>↑</span></div>
<div><strong>Latency</strong><span>↓</span></div>
</div>

</div>
</div>

</div>

<div class="vcm-badges" markdown>
<span>ROI-aware Coding</span>
<span>Compression-domain Vision</span>
<span>Edge VCM</span>
<span>Neural Preprocessing</span>
<span>Benchmarking</span>
</div>

</section>

<section class="vcm-problem-section" markdown>

<div class="vcm-section-heading" markdown>
<div class="vcm-section-label">Research Motivation</div>
## Từ mã hoá cho người xem đến mã hoá cho máy hiểu
</div>

<div class="vcm-two-column" markdown>
<div markdown>
Trong nhiều hệ thống hiện đại, video không còn chỉ được truyền đi để con người quan sát. Video ngày càng được xử lý bởi các mô hình trí tuệ nhân tạo đặt tại camera thông minh, robot, xe tự hành, máy chủ biên hoặc trung tâm phân tích dữ liệu.

Do đó, một hệ thống mã hoá video hiệu quả cần trả lời câu hỏi: **thông tin nào trong video thực sự quan trọng cho tác vụ thị giác máy?**
</div>

<div class="vcm-question-card" markdown>
### Câu hỏi nghiên cứu trung tâm
Làm thế nào để giảm bitrate, độ trễ và chi phí tính toán trong khi vẫn duy trì, hoặc thậm chí cải thiện, độ chính xác của các tác vụ thị giác máy dưới tác động của nén video?
</div>
</div>

</section>

<section class="vcm-metric-strip" markdown>
<div markdown>
<strong>Human-centric coding</strong>
<span>PSNR · MS-SSIM · VMAF</span>
</div>
<div markdown>
<strong>Machine-centric coding</strong>
<span>mAP · mIoU · IDF1 · HOTA · Latency</span>
</div>
<div markdown>
<strong>System-centric coding</strong>
<span>Bitrate · Energy · Memory · Edge Throughput</span>
</div>
</section>

<section class="vcm-research-section" markdown>

<div class="vcm-section-heading" markdown>
<div class="vcm-section-label">Research Directions</div>
## Năm hướng nghiên cứu trọng tâm
</div>

<div class="vcm-direction-grid" markdown>

<div class="vcm-direction-card card-roi" markdown>
<div class="vcm-direction-index">01</div>
### ROI-aware Video Coding
Phân bổ bit theo mức độ quan trọng của vùng ảnh đối với tác vụ máy: đối tượng, vùng chuyển động, vùng rủi ro, vùng ngữ nghĩa.

<span>ROI map · QP control · CTU/CU-level · task-aware rate control</span>
</div>

<div class="vcm-direction-card card-cdv" markdown>
<div class="vcm-direction-index">02</div>
### Compression-domain Vision
Khai thác motion vectors, residuals, transform coefficients và coding modes để phân tích video với chi phí thấp.

<span>motion vector · residual map · coding mode · low-complexity analytics</span>
</div>

<div class="vcm-direction-card card-edge" markdown>
<div class="vcm-direction-index">03</div>
### Edge-oriented VCM
Thiết kế pipeline mã hoá và thị giác máy trên thiết bị biên, cân bằng độ trễ, năng lượng, băng thông và độ chính xác.

<span>Jetson · edge AI · real-time · latency-aware coding</span>
</div>

<div class="vcm-direction-card card-npp" markdown>
<div class="vcm-direction-index">04</div>
### Neural Preprocessing
Dùng mô-đun học sâu để tiền xử lý video trước codec chuẩn, bảo toàn thông tin quan trọng cho mô hình thị giác máy.

<span>wavelet · enhancement · neural-standard hybrid · task preservation</span>
</div>

<div class="vcm-direction-card card-bench" markdown>
<div class="vcm-direction-index">05</div>
### VCM Benchmarking
Xây dựng giao thức đánh giá có khả năng tái lập cho Video Coding for Machines dựa trên cả nén, tác vụ và hệ thống.

<span>BD-rate · mAP · mIoU · tracking · reproducibility</span>
</div>

</div>
</section>

<section class="vcm-framework-section" markdown>

<div class="vcm-section-heading" markdown>
<div class="vcm-section-label">Research Framework</div>
## Khung triển khai nghiên cứu của nhóm
</div>

<div class="vcm-framework" markdown>
<div markdown>
### 1. Problem Formulation
Xác định bài toán, giả thuyết nghiên cứu, khoảng trống học thuật và tiêu chí đánh giá.
</div>
<div markdown>
### 2. Reproducible Baseline
Xây dựng pipeline baseline gồm codec, dataset, mô hình thị giác máy và script đánh giá.
</div>
<div markdown>
### 3. Task-aware Method
Đề xuất cơ chế điều khiển mã hoá dựa trên ROI, đặc trưng miền nén, neural preprocessing hoặc ràng buộc thiết bị biên.
</div>
<div markdown>
### 4. Scientific Evaluation
Đánh giá theo bitrate, task accuracy, latency, complexity, ablation study và phân tích giới hạn.
</div>
</div>

</section>

<section class="vcm-output-section" markdown>

<div class="vcm-output-card" markdown>
### Định hướng đầu ra

| Nhóm đầu ra | Sản phẩm kỳ vọng |
|---|---|
| Công bố khoa học | Bài báo hội nghị, tạp chí, workshop chuyên ngành multimedia và computer vision |
| Mã nguồn | Pipeline mã hoá, script đánh giá, cấu hình thí nghiệm, baseline tái lập |
| Benchmark | Dataset protocol, encoding ladder, metric suite, bảng kết quả chuẩn |
| Đào tạo | Đồ án, luận văn, seminar, slide học thuật, nhóm sinh viên nghiên cứu |

</div>

<div class="vcm-final-cta" markdown>
## Xây dựng một nền tảng nghiên cứu VCM bài bản, mở, tái lập và có khả năng công bố quốc tế.

[Tham gia nhóm nghiên cứu](join-us.md){ .md-button .md-button--primary }
[GitHub Organization](https://github.com/VCM-704LAB-UET){ .md-button .vcm-button-secondary }
</div>

</section>
