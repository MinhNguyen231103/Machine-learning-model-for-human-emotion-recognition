## 📌 Giới thiệu
Đề tài tập trung xây dựng mô hình nhận diện cảm xúc con người từ ảnh khuôn mặt  
dựa trên tập dữ liệu **FER2013**, sử dụng thuật toán học không giám sát **K-Means**.  

Mô hình kết hợp:
- Trích chọn đặc trưng **HOG**
- Giảm chiều dữ liệu bằng **PCA**
- Phân cụm bằng **K-Means** để nhận diện cảm xúc

---

## 📊 Tập dữ liệu FER2013
- Ảnh khuôn mặt thang độ xám **48×48 pixel**
- **7 cảm xúc:**
  - Angry
  - Disgust
  - Fear
  - Happy
  - Sad
  - Surprise
  - Neutral

**Số lượng dữ liệu:**
- 28.709 ảnh huấn luyện
- 3.589 ảnh kiểm tra

---

## 🧠 Phương pháp thực hiện

### 1️⃣ Trích chọn đặc trưng HOG
HOG (Histogram of Oriented Gradients) được sử dụng để mô tả cấu trúc  
và biên cạnh của khuôn mặt.

**Các bước chính:**
- Chuyển ảnh sang ảnh xám
- Chuẩn hóa kích thước
- Tính gradient
- Chia cell và histogram hướng
