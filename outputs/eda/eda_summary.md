# Tổng hợp EDA GTSRB

- Train: 39,209 ảnh; test: 12,630 ảnh; 43 lớp.
- Tỷ lệ số mẫu train giữa lớp lớn nhất/nhỏ nhất: 10.71 lần.
- Đã quét 51,839 ảnh. Quét đầy đủ: True.
- Ảnh không đọc được: 0; sai kích thước so với CSV: 0.
- Metadata mô tả bị thiếu: 1 giá trị; xem missing_values_by_column.csv.
- Metadata có kích thước/ROI bất thường: 0 dòng.
- Nhóm trùng pixel: 8; trùng train/test: 8; nhãn mâu thuẫn: 0.
- Nhóm ảnh ứng viên suy ra từ tên tệp train: 1307.

## Việc cần thực hiện trước huấn luyện

1. Xem ảnh lỗi, metadata bất thường, ảnh trùng và nhãn mâu thuẫn nếu có. Không tự động xóa ảnh.
2. Giữ test riêng; chia validation từ train. Xác nhận nhóm ảnh và xem xét chia theo nhóm; kiểm tra trùng pixel giữa các tập mới.
3. Giữ RGB; chọn resize và chuẩn hóa phù hợp CNN hoặc trọng số VGG16. Thống kê chuẩn hóa và trọng số lớp chỉ tính từ train sau khi chia.
4. Huấn luyện CNN cơ sở với xử lý tối thiểu trước. Sau đó thử augmentation nhẹ trên train; tránh lật hướng hoặc cắt mất ký hiệu.
5. Báo cáo accuracy, macro-F1, recall từng lớp và confusion matrix. Nếu cần, thử class weighting riêng để đo tác dụng.
6. Ảnh tối, sáng hoặc ít tương phản vẫn có thể hợp lệ. Ngưỡng EDA không phải quy tắc loại bỏ ảnh.

Hash chỉ phát hiện ảnh trùng pixel chính xác. Nếu chạy mẫu, cần quét lại toàn bộ trước khi kết luận.
