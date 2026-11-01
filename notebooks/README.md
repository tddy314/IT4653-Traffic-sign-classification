# Notebook EDA GTSRB

Mở `01_gtsrb_eda.ipynb` trong VS Code hoặc Jupyter, chọn Python của dự án tại
`../.venv/Scripts/python.exe`, rồi chạy **Run All** từ trên xuống.

Notebook tự tìm `data/raw/gtsrb` từ thư mục làm việc và các thư mục cha. Có thể
mở từ thư mục gốc dự án hoặc `notebooks/`.

## Google Colab

Chạy ô thiết lập có hàm `find_root()` trước các ô phân tích. Nếu chưa có dữ liệu,
notebook tự tải GTSRB từ Kaggle vào `/content/data/raw/gtsrb`. Kết quả được ghi
vào `/content/outputs/eda/`. Máy Colab không tự truy cập dữ liệu ở ổ D: của máy
cá nhân; `/content` cũng là bộ nhớ tạm của phiên, vì vậy cần tải kết quả về hoặc
sao lưu trước khi kết thúc phiên.

## Môi trường

Môi trường `.venv` hiện tại sử dụng lại các thư viện phân tích đã cài ở Python
gốc và cài các thư viện Jupyter bổ sung trong dự án. Để tạo một môi trường độc
lập trên máy khác, chạy từ thư mục gốc dự án:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements-eda.txt
```

## Kết quả

- Các bảng CSV và bản tổng hợp: `outputs/eda/`.
- Biểu đồ PNG: `outputs/eda/figures/`.
- Kết luận tự động từ kết quả chạy: `outputs/eda/eda_summary.md`.
- `FULL_IMAGE_SCAN = True` quét toàn bộ ảnh; đặt `False` để chạy thử bằng mẫu.

Mỗi lần chạy sẽ ghi lại các kết quả trong `outputs/eda/`. Notebook không sửa
dữ liệu gốc, chưa chia validation, chưa augmentation và chưa huấn luyện mô hình.
