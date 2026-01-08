📌 Giới thiệu
Đề tài tập trung xây dựng mô hình nhận diện cảm xúc con người từ ảnh khuôn mặt dựa trên tập dữ liệu FER2013, sử dụng thuật toán học không giám sát K-Means. Mô hình kết hợp trích chọn đặc trưng HOG, giảm chiều dữ liệu bằng PCA và phân cụm K-Means để nhận diện cảm xúc.

📊 Tập dữ liệu FER2013
Ảnh khuôn mặt thang độ xám 48×48 pixel
7 cảm xúc:
Angry, Disgust, Fear, Happy, Sad, Surprise, Neutral
Số lượng dữ liệu: 
- 28.709 ảnh huấn luyện
- 3.589 ảnh kiểm tra

🧠 Phương pháp thực hiện
1️⃣ Trích chọn đặc trưng HOG
HOG (Histogram of Oriented Gradients) được sử dụng để mô tả cấu trúc và biên cạnh khuôn mặt.
Các bước chính:
- Chuyển ảnh về ảnh xám
- Chuẩn hóa kích thước ảnh
- Tính gradient theo hướng và độ lớn
- Chia ảnh thành các cell
- Chia hướng gradient thành 9 bins (0–180°)
- Xây dựng vector đặc trưng cho mỗi ảnh

2️⃣ Giảm chiều dữ liệu PCA
PCA (Principal Component Analysis) giúp giảm số chiều dữ liệu nhưng vẫn giữ lại thông tin quan trọng.
Các bước:
- Chuẩn hóa dữ liệu
- Tính ma trận hiệp phương sai
- Tính eigenvalues và eigenvectors
- Sắp xếp các thành phần chính theo thứ tự giảm dần
- Chọn số lượng thành phần chính
- Chuyển đổi dữ liệu

3️⃣ Thuật toán K-Means
K-Means là thuật toán phân cụm không giám sát, chia dữ liệu thành K cụm dựa trên khoảng cách đến tâm cụm.
Quy trình:
- Khởi tạo K tâm cụm
- Gán các điểm dữ liệu vào cụm gần nhất
- Cập nhật tâm cụm bằng giá trị trung bình
- Lặp lại đến khi hội tụ hoặc đạt số vòng lặp tối đa (100)
