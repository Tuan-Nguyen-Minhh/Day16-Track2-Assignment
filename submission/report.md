# Báo cáo kết quả Benchmark LightGBM - Lab 16

1. Tôi dùng AWS, region us-east-1, EC2 instance t3.medium (Compute) & t3.micro (Bastion), mã nguồn hạ tầng tại `submission/infra/`.
2. Dataset Credit Card Fraud có 284.807 dòng (492 fraud), chia train/validation/test là 170.883 / 56.962 / 56.962 với seed 16.
3. Load dữ liệu mất 2,70 giây; training mất 3,56 giây; best iteration là 68.
4. Kết quả test: AUC 0,9768, Accuracy 0,9995, F1 0,8478, Precision 0,9070, Recall 0,7959.
5. Latency 1 dòng 1,21 ms; throughput batch 1.000 dòng đạt 300.947,7 dòng/giây (đo median, predict_proba).
6. CPU/RAM/Network: Biểu đồ tài nguyên ghi nhận hoạt động ổn định được đính kèm tại `submission/screenshots/tai_nguyen1.png` (Bastion Host) và `submission/screenshots/tai_nguyen2.png` (Compute Node).
7. Billing: đã bị trừ 0.2 đô tại vì sử dụng các dịch vụ của ec2
8. Hạ tầng đã được dọn dẹp hoàn tất bằng `terraform destroy` (27 resources destroyed), xác nhận cả 2 máy chủ đều ở trạng thái Terminated trong ảnh `tai_nguyen1.png` và `tai_nguyen2.png`.