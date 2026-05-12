---
title: Giới thiệu
---

# Giới thiệu VCM-704LAB-UET

**VCM-704LAB-UET** là nhóm nghiên cứu định hướng về **Video Coding for Machines (VCM)** tại Trường Đại học Công nghệ, Đại học Quốc gia Hà Nội. Nhóm tập trung vào việc nghiên cứu, phát triển và đánh giá các phương pháp mã hoá video phục vụ các hệ thống thị giác máy, đặc biệt trong bối cảnh video được xử lý bởi mô hình trí tuệ nhân tạo, thiết bị biên và hệ thống phân tích video quy mô lớn.

## Bối cảnh nghiên cứu

Các chuẩn mã hoá video truyền thống như H.264/AVC, H.265/HEVC và H.266/VVC chủ yếu được thiết kế để tối ưu chất lượng cảm nhận của con người dưới ràng buộc bitrate. Tuy nhiên, trong nhiều hệ thống hiện đại, video không chỉ được dùng để con người quan sát mà còn là đầu vào cho các mô hình thị giác máy như:

- phát hiện đối tượng,
- phân đoạn ngữ nghĩa hoặc phân đoạn thực thể,
- theo vết đa đối tượng,
- nhận dạng hành động và sự kiện,
- nhận thức môi trường cho robot và xe tự hành,
- kiểm tra công nghiệp và giám sát thông minh.

Trong các ứng dụng này, chất lượng thị giác cao chưa chắc tương ứng với hiệu năng tác vụ máy cao. Một số chi tiết có thể ít quan trọng với người xem nhưng lại rất quan trọng với mô hình AI; ngược lại, một số vùng nền tiêu tốn nhiều bitrate nhưng đóng góp ít vào kết quả phân tích. Điều này tạo ra nhu cầu nghiên cứu một thế hệ hệ thống mã hoá mới: **mã hoá video hướng tác vụ**.

## Tầm nhìn

Tầm nhìn của VCM-704LAB-UET là xây dựng một nền tảng nghiên cứu bài bản về **mã hoá video cho thị giác máy**, trong đó các phương pháp mã hoá được thiết kế không chỉ để giảm dung lượng video mà còn để bảo toàn thông tin có ích cho mô hình AI, giảm độ trễ, giảm chi phí tính toán và tăng khả năng triển khai thực tế.

Nhóm hướng tới các phương pháp có ba đặc điểm:

| Đặc điểm | Ý nghĩa |
|---|---|
| Task-aware | Quá trình mã hoá xem xét trực tiếp ảnh hưởng đến tác vụ thị giác máy |
| Standard-compatible | Ưu tiên các giải pháp có thể tích hợp hoặc mở rộng từ codec chuẩn như HEVC/VVC |
| Reproducible | Thí nghiệm, mã nguồn, cấu hình và kết quả được tổ chức để có thể tái lập |

## Sứ mệnh nghiên cứu

Sứ mệnh của nhóm là phát triển các phương pháp, công cụ và giao thức đánh giá giúp trả lời những câu hỏi cốt lõi sau:

1. **Thông tin nào trong video là quan trọng đối với mô hình thị giác máy?**  
   Nhóm nghiên cứu các cách xác định vùng, khung hình, chuyển động hoặc đặc trưng miền nén có ảnh hưởng lớn đến độ chính xác của tác vụ.

2. **Làm thế nào để điều khiển codec theo mục tiêu tác vụ?**  
   Nhóm tập trung vào các cơ chế điều chỉnh bitrate, QP, CTU/CU-level control, ROI map và rate control dựa trên ngữ nghĩa hoặc rủi ro tác vụ.

3. **Có thể khai thác trực tiếp thông tin trong miền nén hay không?**  
   Các thành phần như motion vector, residual, coding mode và partition structure có thể được sử dụng như tín hiệu phụ trợ cho phân tích video chi phí thấp.

4. **Làm thế nào để triển khai VCM trên thiết bị biên?**  
   Nhóm nghiên cứu cân bằng giữa bitrate, độ trễ, năng lượng, bộ nhớ và độ chính xác mô hình trong các pipeline edge AI.

5. **Đánh giá VCM như thế nào cho đúng?**  
   Ngoài PSNR, MS-SSIM và VMAF, nhóm sử dụng các chỉ số tác vụ như mAP, mIoU, IDF1, HOTA, latency và BD-rate theo task accuracy.

## Định vị học thuật

VCM-704LAB-UET nằm tại giao điểm của các lĩnh vực:

- video coding và multimedia systems,
- computer vision và machine learning,
- edge computing và embedded AI,
- task-oriented communication,
- reproducible benchmarking.

Nhóm không chỉ hướng tới việc tạo ra demo hoặc ứng dụng ngắn hạn, mà còn xây dựng các đóng góp học thuật có thể công bố tại hội nghị, workshop và tạp chí chuyên ngành về multimedia, image/video processing, computer vision và intelligent systems.

## Nguyên tắc làm việc

Nhóm vận hành theo bốn nguyên tắc:

### 1. Bài toán rõ ràng
Mỗi hướng nghiên cứu phải bắt đầu từ một câu hỏi khoa học cụ thể, có phân tích khoảng trống và có baseline để so sánh.

### 2. Thực nghiệm có kiểm soát
Mọi kết quả phải gắn với dataset, codec, cấu hình mã hoá, mô hình thị giác máy, script đánh giá và log thí nghiệm.

### 3. Mã nguồn có khả năng tái lập
Code cần có cấu trúc rõ, hướng dẫn chạy, file cấu hình, script reproduce và bảng kết quả.

### 4. Đầu ra học thuật
Mỗi dự án cần hướng tới ít nhất một trong các đầu ra: technical report, open-source baseline, benchmark, seminar, đồ án, luận văn hoặc bài báo.

## Đầu ra kỳ vọng

| Nhóm đầu ra | Mô tả |
|---|---|
| Công bố khoa học | Bài báo hội nghị, workshop, tạp chí trong lĩnh vực multimedia và computer vision |
| Mã nguồn mở | Pipeline mã hoá, đánh giá, benchmark và script tái lập |
| Benchmark | Giao thức đánh giá cho VCM trên detection, segmentation, tracking và edge analytics |
| Đào tạo | Sinh viên nghiên cứu, đồ án, luận văn, seminar học thuật |
| Hợp tác | Kết nối với nhóm nghiên cứu, doanh nghiệp và dự án ứng dụng liên quan video analytics |
