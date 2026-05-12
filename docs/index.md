---
title: Trang chủ
hide:
  - toc
---

<section class="vcm-hero" markdown>
<div class="vcm-hero-content" markdown>

<div class="vcm-kicker">VCM-704LAB-UET · Video Coding for Machines</div>

# Mã hoá video cho thị giác máy

## Tối ưu hoá biểu diễn video cho các hệ thống trí tuệ nhân tạo, thiết bị biên và phân tích thị giác quy mô lớn.

**VCM-704LAB-UET** là nhóm nghiên cứu tập trung vào **Video Coding for Machines (VCM)** — một hướng nghiên cứu mới nhằm thiết kế, cải tiến và đánh giá các hệ thống mã hoá video không chỉ cho người xem, mà còn cho các mô hình thị giác máy như phát hiện đối tượng, phân đoạn ngữ nghĩa, theo vết, nhận dạng sự kiện và hệ thống tự hành.

<div class="vcm-hero-actions" markdown>
[Khám phá hướng nghiên cứu](research.md){ .md-button .md-button--primary }
[Xem dự án](projects.md){ .md-button }
</div>

</div>

<div class="vcm-hero-panel" markdown>

### Trọng tâm nghiên cứu

- ROI-aware video coding
- Compression-domain vision analytics
- Edge-oriented VCM
- Neural preprocessing for standard codecs
- Benchmarking and evaluation for VCM

</div>
</section>

---

<section class="vcm-section" markdown>

## Vì sao cần Video Coding for Machines?

Trong các hệ thống video truyền thống, bộ mã hoá thường được tối ưu theo chất lượng cảm nhận của con người, ví dụ PSNR, MS-SSIM hoặc VMAF. Tuy nhiên, trong nhiều ứng dụng hiện đại, video được truyền đi chủ yếu để **máy phân tích**: camera thông minh, robot, xe tự hành, giám sát đô thị, kiểm tra công nghiệp, thiết bị biên và hệ thống phân tích video thời gian thực.

Khi đó, câu hỏi nghiên cứu không còn chỉ là:

> Làm thế nào để video nhìn đẹp hơn với cùng bitrate?

mà trở thành:

> Làm thế nào để mã hoá video sao cho giữ được nhiều nhất thông tin hữu ích cho tác vụ thị giác máy, trong khi vẫn giảm bitrate, độ trễ và chi phí tính toán?

</section>

<div class="vcm-stat-grid" markdown>

<div class="vcm-stat-card" markdown>
<span class="vcm-stat-number">01</span>
### Task-aware Coding
Mã hoá theo mức độ quan trọng đối với tác vụ máy thay vì chỉ theo chất lượng thị giác con người.
</div>

<div class="vcm-stat-card" markdown>
<span class="vcm-stat-number">02</span>
### Standard-compatible
Ưu tiên các phương pháp tương thích hoặc mở rộng từ HEVC/VVC/H.26x để tăng khả năng ứng dụng.
</div>

<div class="vcm-stat-card" markdown>
<span class="vcm-stat-number">03</span>
### Edge-efficient
Cân bằng bitrate, độ trễ, năng lượng, bộ nhớ và độ chính xác mô hình trên thiết bị biên.
</div>

<div class="vcm-stat-card" markdown>
<span class="vcm-stat-number">04</span>
### Reproducible Research
Xây dựng pipeline, benchmark, mã nguồn và giao thức đánh giá có khả năng tái lập.
</div>

</div>

---

## Các hướng nghiên cứu chính

<div class="vcm-card-grid" markdown>

<div class="vcm-research-card" markdown>
<div class="vcm-card-label">Direction 01</div>
### ROI-aware Video Coding
Nghiên cứu cơ chế phân bổ bit thông minh cho các vùng quan trọng đối với tác vụ máy, chẳng hạn đối tượng, vùng chuyển động, vùng rủi ro hoặc vùng ngữ nghĩa.

**Từ khóa:** ROI map, QP control, CTU/CU-level coding, task-aware rate control.
</div>

<div class="vcm-research-card" markdown>
<div class="vcm-card-label">Direction 02</div>
### Compression-domain Analytics
Khai thác thông tin có sẵn trong miền nén như motion vectors, residuals, transform coefficients, partition maps và coding modes để hỗ trợ phân tích thị giác chi phí thấp.

**Từ khóa:** motion vector, residual map, coding mode, compressed-domain vision.
</div>

<div class="vcm-research-card" markdown>
<div class="vcm-card-label">Direction 03</div>
### Edge-oriented VCM
Thiết kế pipeline mã hoá và phân tích video cho thiết bị biên, nơi tài nguyên tính toán, băng thông, năng lượng và độ trễ đều bị giới hạn.

**Từ khóa:** Jetson, real-time analytics, edge-server collaboration, latency-aware coding.
</div>

<div class="vcm-research-card" markdown>
<div class="vcm-card-label">Direction 04</div>
### Neural Preprocessing
Phát triển các mô-đun tiền xử lý dùng học sâu trước khi đưa video vào codec chuẩn nhằm bảo toàn thông tin quan trọng cho mô hình thị giác máy.

**Từ khóa:** neural preprocessing, wavelet, enhancement, hybrid neural-standard coding.
</div>

<div class="vcm-research-card" markdown>
<div class="vcm-card-label">Direction 05</div>
### VCM Benchmarking
Xây dựng giao thức đánh giá có khả năng tái lập cho VCM, kết hợp chỉ số nén với chỉ số tác vụ như mAP, mIoU, MOTA, IDF1 và latency.

**Từ khóa:** BD-rate for machine tasks, reproducibility, benchmark protocol.
</div>

</div>

---

## Triết lý nghiên cứu

<div class="vcm-principle-grid" markdown>

<div markdown>
### 1. Học thuật có cơ sở
Mỗi đề xuất phải xuất phát từ một câu hỏi nghiên cứu rõ ràng, có phân tích khoảng trống, có baseline và có luận điểm khoa học kiểm chứng được.
</div>

<div markdown>
### 2. Thực nghiệm có khả năng tái lập
Mọi kết quả cần đi kèm dataset, cấu hình codec, model thị giác máy, script đánh giá, log thí nghiệm và bảng phân tích đầy đủ.
</div>

<div markdown>
### 3. Hướng tới ứng dụng thực tế
Các phương pháp được ưu tiên nếu có khả năng tương thích codec chuẩn, triển khai trên thiết bị biên hoặc tích hợp vào hệ thống phân tích video thực tế.
</div>

</div>

---

## Không gian làm việc nghiên cứu

Nhóm sử dụng GitHub như một **research workspace** để quản lý mã nguồn, tài liệu, tiến độ, kết quả thí nghiệm và bản thảo học thuật.

| Thành phần | Vai trò |
|---|---|
| GitHub Organization | Không gian chung cho toàn bộ lab |
| Project Board | Quản lý task, milestone và tiến độ hằng tuần |
| Research Repositories | Lưu code, config, script và kết quả thí nghiệm |
| Reading List | Tổng hợp paper, survey, benchmark và dataset |
| Papers & Reports | Quản lý manuscript, slide, poster và technical report |

<div class="vcm-footer-cta" markdown>
### Hướng tới một nền tảng nghiên cứu VCM bài bản, tái lập và có khả năng công bố quốc tế.

[Tham gia nhóm nghiên cứu](join-us.md){ .md-button .md-button--primary }
[GitHub Organization](https://github.com/VCM-704LAB-UET){ .md-button }
</div>
