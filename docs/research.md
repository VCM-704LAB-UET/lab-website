---
title: Hướng nghiên cứu
---

# Hướng nghiên cứu

VCM-704LAB-UET tập trung vào **Video Coding for Machines (VCM)** — hướng nghiên cứu nhằm tối ưu hoá quá trình mã hoá video cho các tác vụ thị giác máy. Thay vì chỉ tối ưu chất lượng cảm nhận của con người, VCM đặt trọng tâm vào việc bảo toàn thông tin có ích cho mô hình AI dưới các ràng buộc về bitrate, độ trễ, năng lượng, tài nguyên tính toán và khả năng triển khai.

## Khung nghiên cứu tổng quát

Một hệ thống VCM có thể được nhìn như một vòng lặp gồm bốn thành phần:

```text
Video input
    ↓
Task-relevant information estimation
    ↓
Codec control / preprocessing / compressed-domain representation
    ↓
Machine vision task evaluation
```

Mục tiêu của nhóm là nghiên cứu các phương pháp tác động vào một hoặc nhiều thành phần trong pipeline này để đạt được sự cân bằng tốt hơn giữa **compression efficiency** và **machine task utility**.

---

## 1. ROI-aware Video Coding for Machine Vision

### Mục tiêu

Hướng này nghiên cứu cách phân bổ tài nguyên mã hoá không đồng đều theo mức độ quan trọng của từng vùng trong video đối với tác vụ thị giác máy. Các vùng chứa đối tượng, vùng chuyển động, vùng có rủi ro cao hoặc vùng có ý nghĩa ngữ nghĩa quan trọng có thể được mã hoá với chất lượng cao hơn, trong khi vùng nền ít quan trọng có thể được nén mạnh hơn.

### Câu hỏi nghiên cứu

- ROI nên được xác định từ detector, segmentation model, motion field, saliency map hay thông tin miền nén?
- Nên điều khiển chất lượng ở mức frame, CTU, CU, object-level hay semantic-region level?
- Làm thế nào để lan truyền ROI theo thời gian nhằm tránh dao động chất lượng giữa các frame?
- Làm thế nào để thiết kế hàm tối ưu cân bằng giữa bitrate và task accuracy?
- ROI coding có ảnh hưởng thế nào đến chất lượng người xem trong các hệ thống human-machine collaborative analytics?

### Hướng tiếp cận kỹ thuật

| Thành phần | Nội dung nghiên cứu |
|---|---|
| ROI estimation | Xây dựng bản đồ quan trọng từ object detector, segmentation, tracking, motion hoặc risk map |
| QP control | Điều chỉnh QP ở mức CTU/CU/object dựa trên mức độ quan trọng |
| Temporal smoothing | Làm mượt ROI và QP theo thời gian để giảm flickering và bất ổn task accuracy |
| Rate control | Phân bổ bitrate theo ràng buộc tổng thể của hệ thống |
| Evaluation | Đánh giá bằng mAP, mIoU, tracking metrics, bitrate và BD-rate theo task |

### Đầu ra kỳ vọng

- Baseline ROI-aware coding tương thích HEVC/VVC.
- Script sinh ROI map từ detector hoặc ground truth.
- Module điều khiển QP theo ROI.
- Báo cáo thực nghiệm bitrate–accuracy.
- Bài báo về task-aware bit allocation.

---

## 2. Compression-domain Vision Analytics

### Mục tiêu

Hướng này nghiên cứu cách khai thác trực tiếp thông tin đã tồn tại trong bitstream hoặc quá trình mã hoá, thay vì luôn giải mã toàn bộ video về pixel domain. Các tín hiệu như motion vector, residual, transform coefficient, partition map và coding mode có thể phản ánh chuyển động, biên, sai khác dự đoán hoặc cấu trúc nội dung.

### Câu hỏi nghiên cứu

- Motion vector có thể thay thế hoặc hỗ trợ optical flow trong các tác vụ tracking và motion analysis hay không?
- Residual có thể dùng để phát hiện vùng mới xuất hiện, vùng chuyển động hoặc vùng bất thường không?
- Coding mode và partition structure có tương quan với độ phức tạp không gian hoặc ngữ nghĩa của nội dung không?
- Có thể thiết kế mô hình thị giác nhẹ sử dụng kết hợp pixel-domain và compression-domain features hay không?

### Hướng tiếp cận kỹ thuật

| Tín hiệu miền nén | Vai trò tiềm năng |
|---|---|
| Motion vector | Ước lượng chuyển động, tracking, temporal propagation |
| Residual map | Phát hiện vùng khó dự đoán, vùng thay đổi hoặc vùng chứa thông tin mới |
| Transform coefficients | Phân tích năng lượng tần số, texture và artifact |
| Coding modes | Gợi ý độ phức tạp nội dung và cấu trúc dự đoán |
| Partition maps | Phản ánh mức chi tiết không gian và biên đối tượng |

### Đầu ra kỳ vọng

- Tool trích xuất đặc trưng miền nén từ HEVC/VVC/H.264.
- Phân tích tương quan giữa compression-domain features và task accuracy.
- Mô hình lightweight analytics sử dụng motion/residual/coding features.
- Bài báo về low-complexity compressed-domain VCM.

---

## 3. Edge-oriented Video Coding and Analytics

### Mục tiêu

Hướng này tập trung vào các hệ thống video thông minh triển khai trên thiết bị biên, nơi tài nguyên tính toán, bộ nhớ, năng lượng, băng thông và độ trễ đều bị giới hạn. Thay vì tối ưu codec và mô hình AI riêng rẽ, nhóm nghiên cứu cách đồng thiết kế pipeline mã hoá–truyền tải–phân tích.

### Câu hỏi nghiên cứu

- Nên xử lý phần nào tại edge device và phần nào tại server?
- Làm thế nào để điều chỉnh bitrate theo độ khó của cảnh và yêu cầu tác vụ?
- Có thể dùng thông tin từ mô hình AI để điều khiển encoder theo thời gian thực hay không?
- Trade-off giữa bitrate, latency, FPS, energy và accuracy nên được mô hình hoá như thế nào?

### Hướng tiếp cận kỹ thuật

| Lớp hệ thống | Nội dung nghiên cứu |
|---|---|
| Video pipeline | Decode, preprocess, encode, transmit, infer |
| Edge hardware | Jetson Nano/Orin, GPU/CPU profiling, memory usage |
| Adaptive coding | Điều chỉnh bitrate/QP/GOP theo task feedback |
| Collaborative analytics | Chia việc giữa edge và server |
| System metrics | FPS, latency, energy, memory, throughput, accuracy |

### Đầu ra kỳ vọng

- Pipeline edge VCM chạy thực tế trên thiết bị biên.
- Benchmark latency–bitrate–accuracy.
- Báo cáo profiling tài nguyên phần cứng.
- Demo real-time video analytics dưới ràng buộc băng thông.

---

## 4. Neural Preprocessing for Standard Codecs

### Mục tiêu

Hướng này nghiên cứu các mô-đun học sâu tiền xử lý video trước khi đưa vào codec chuẩn. Thay vì thay thế hoàn toàn HEVC/VVC bằng learned codec, cách tiếp cận này giữ tính tương thích chuẩn nhưng bổ sung khả năng làm nổi bật hoặc bảo toàn thông tin có ích cho tác vụ máy.

### Câu hỏi nghiên cứu

- Neural preprocessing có thể cải thiện task accuracy sau nén mà không làm tăng bitrate đáng kể không?
- Nên tối ưu preprocessing theo perceptual quality, task loss hay kết hợp cả hai?
- Các biểu diễn wavelet, frequency-domain hoặc attention-based có giúp chống suy giảm do nén không?
- Làm thế nào để thiết kế mô hình đủ nhẹ cho edge deployment?

### Hướng tiếp cận kỹ thuật

| Thành phần | Nội dung nghiên cứu |
|---|---|
| Preprocessing network | Enhancement, denoising, feature-preserving transformation |
| Wavelet/frequency module | Khai thác miền tần số để bảo toàn chi tiết có ích |
| Task loss | Tối ưu theo detection/segmentation/tracking accuracy |
| Codec compatibility | Đầu ra vẫn được mã hoá bằng codec chuẩn |
| Lightweight design | Giảm số tham số, FLOPs và latency |

### Đầu ra kỳ vọng

- Baseline neural preprocessing + HEVC/VVC.
- So sánh task accuracy trước và sau preprocessing.
- Ablation study về loss, kiến trúc và bitrate.
- Bài báo về hybrid neural-standard VCM.

---

## 5. Benchmarking and Evaluation for VCM

### Mục tiêu

Một thách thức lớn của VCM là đánh giá. Nếu chỉ dùng PSNR hoặc VMAF, ta có thể bỏ qua ảnh hưởng thật sự của nén lên mô hình thị giác máy. Vì vậy, nhóm xây dựng benchmark và giao thức đánh giá kết hợp cả chỉ số nén, chỉ số tác vụ và chỉ số hệ thống.

### Câu hỏi nghiên cứu

- Dataset nào phù hợp cho detection, segmentation, tracking và autonomous perception dưới nén?
- Encoding ladder nên được thiết kế như thế nào để so sánh công bằng?
- Làm thế nào để tính BD-rate theo mAP, mIoU hoặc tracking metrics?
- Cần ghi nhận metadata nào để kết quả có khả năng tái lập?

### Bộ chỉ số đánh giá

| Nhóm chỉ số | Ví dụ |
|---|---|
| Compression | bitrate, bpp, PSNR, MS-SSIM, VMAF |
| Detection | mAP, AP50, AP75 |
| Segmentation | mIoU, pixel accuracy |
| Tracking | MOTA, IDF1, HOTA |
| Edge/system | FPS, latency, memory, energy |
| VCM trade-off | BD-rate versus task accuracy |

### Đầu ra kỳ vọng

- Bộ script encode/evaluate thống nhất.
- Giao thức benchmark cho nhiều dataset và codec.
- Bảng kết quả baseline công khai.
- Reproducibility checklist cho từng thí nghiệm.

---

## Tích hợp các hướng nghiên cứu

Các hướng nghiên cứu không tách rời mà bổ trợ cho nhau:

| Hướng | Đóng góp vào hệ sinh thái VCM |
|---|---|
| ROI-aware coding | Điều khiển phân bổ bitrate theo thông tin quan trọng |
| Compression-domain analytics | Cung cấp tín hiệu chi phí thấp cho task-awareness |
| Edge-oriented VCM | Đưa phương pháp vào bối cảnh triển khai thực tế |
| Neural preprocessing | Tăng khả năng bảo toàn thông tin trước mã hoá |
| Benchmarking | Đảm bảo đánh giá công bằng, tái lập và có giá trị học thuật |

Mục tiêu dài hạn là hình thành một hệ sinh thái nghiên cứu trong đó mỗi đề xuất mới đều có baseline, giao thức đánh giá, phân tích giới hạn và khả năng mở rộng thành bài báo khoa học.