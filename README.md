# 🔬 Lab 7: AIoT Computer Vision Model Zoo

Dự án này là một thư viện thu nhỏ (Model Zoo) dành riêng cho các ứng dụng AIoT. Mục tiêu không chỉ dừng lại ở việc đếm hay nhận diện vật thể bằng YOLO, mà là đánh giá toàn diện các dạng đầu ra (outputs) của Computer Vision để chọn đúng công cụ cho từng bài toán cụ thể.

---

## 🧩 Tổng quan các Engine Xử lý

Hệ thống cung cấp một loạt các bài toán cốt lõi, mỗi bài toán phục vụ một mục đích cụ thể trong kiến trúc AIoT:

| Tên Mô Hình | Dữ liệu Đầu ra (Output) | Ứng dụng Thực tiễn |
| :--- | :--- | :--- |
| **YOLO Detection** | Bounding box, Class, Confidence | Tìm vị trí và phân loại đối tượng trong khung hình. |
| **Tracking / Counting**| Object ID, Centroid, Count | Theo dõi luồng di chuyển, đếm số lượng qua vạch. |
| **Segmentation** | Mask, Mask area, Region bbox | Tách viền chính xác. Rất phù hợp để đo lường diện tích vùng lây nhiễm bệnh trên lá cây trong hệ thống AgriSense. |
| **OCR** | Text, Text bbox, Confidence | Số hóa văn bản từ hình ảnh (biển số, nhãn mác). |
| **OpenCV Motion** | Motion area, Motion bbox | Nhận diện chuyển động nhẹ để đánh thức các model AI nặng. |
| **Pose / Hand / Face** | Landmarks, Labels, Attention cue | Giao tiếp người-máy (HCI), theo dõi mức độ tập trung. |

---

## 🚀 Hướng dẫn Triển khai Nhanh

Khởi tạo môi trường và chạy thử nghiệm cục bộ chỉ với vài dòng lệnh.

**Bước 1: Chuẩn bị môi trường**
```bash
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements_core.txt
**Bước 2: Xác thực Pipeline**
python run_model_zoo_demo.py
**Bước 3: Khởi chạy Dashboard Web**
uvicorn app:app --reload --host 127.0.0.1 --port 8000
