# Lab4_Image_Segemetationn
# Công nghệ sử dụng
Ngôn ngữ: Python Thư viện: Pillow (PIL): xử lý ảnh cơ bản như đọc, chuyển đổi và lưu ảnh.

NumPy: xử lý mảng ảnh dạng ma trận.

Matplotlib: hiển thị ảnh.

imageio: đọc ảnh theo chuẩn imageio (nếu cần).

scipy.ndimage là một module trong thư viện SciPy, dùng để xử lý ảnh

threshold_otsu là một hàm dùng để tự động tìm ngưỡng phân tách (threshold) tối ưu giữa hai lớp điểm ảnh (foreground và background) trong ảnh xám, dựa trên phương pháp Otsu

# Title
# Phân vùng theo histogram
Một ngưỡng được xác định dựa theo histogram của ảnh. Mỗi pixel trong ảnh được so sánh với
ngưỡng, nếu giá trị pixel nhỏ hơn ngưỡng, thì pixel trong phân vùng được gán giá trị 0. Ngược
lại, gán giá trị 1.

# Giải thích cách hoạt động
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/c60df6d3-0e8e-416d-8bd9-9f5f4f35283a)
2. ** Đọc ảnh từ file ảnh - chuyển sang ảnh xám - chuyển thành dạng numpy
![image](https://github.com/user-attachments/assets/ac68939a-e162-46d1-a465-0d3ed1661acb)
3. ** Tìm ngưỡng otsu
![image](https://github.com/user-attachments/assets/2e3d6150-64c1-45e1-9c10-6c6cf9a5002f)
4. ** Tạo ảnh nhị phân
![image](https://github.com/user-attachments/assets/e8d01553-b3a9-4e06-b15d-ce366f786d84)
5. Chuyển về ảnh và hiển thị
![image](https://github.com/user-attachments/assets/3c0882a2-c176-4af3-834f-07ed2ef0a90b)

# Phương pháp Adaptive threshholding
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/f9722e77-b677-4845-9933-e1669cc92f3f)
2.** Đọc ảnh từ file ảnh - chuyển sang ảnh xám - chuyển thành dạng numpy
![image](https://github.com/user-attachments/assets/333a1432-0102-47ec-8c65-1b7118d4e1db)
3. ** Tính ngưỡng otsu
![image](https://github.com/user-attachments/assets/594e133f-90ce-47d4-9c14-0ea250e3542c)
4. ** Chuyển về ảnh và hiển thị
![image](https://github.com/user-attachments/assets/5fa7c718-80dc-4312-88a9-224a8f8a114e)

# Phân vùng theo region
Một region là một nhóm các pixel có cùng thuộc tính.

# Giải thích cách hoạt động
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/3e1f6875-e4dd-4e60-9975-d3c58543a575)
2. ** Dùng thư viện cv2 để đọc ảnh
![image](https://github.com/user-attachments/assets/d52afdb6-1fad-4f53-a877-82f46da33ab9)
3. ** Chuyển về ảnh xám màu
![image](https://github.com/user-attachments/assets/eed91947-4acc-4f45-a1bb-074530a6693d)
4. ** Ngưỡng otsu để đảo ảnh
![image](https://github.com/user-attachments/assets/e9b383c0-1c95-4aef-844f-2320dfac4d2a)
5. ** Làm nhỏ các vùng có nền trắng, để tách rời đối tượng liền nhau
![image](https://github.com/user-attachments/assets/ef93f856-32f9-4164-9ea0-ca78e4280c0a)
6. ** Biến đổi khoảng cách mỗi pixel 
![image](https://github.com/user-attachments/assets/21836bb8-d108-4f1d-b33b-b8a4bd441726)
7. ** Ngưỡng vùng foreground
![image](https://github.com/user-attachments/assets/5b1c2775-816c-4e5d-a4e6-a6219664a5c7)
8. ** Gán nhãn label(dt) cho từng vùng
![image](https://github.com/user-attachments/assets/7836ecfa-3bc2-45f2-9dcc-09c519def384)
9. ** Chuyển nhãn sang kiểu int32
![image](https://github.com/user-attachments/assets/695180ff-b333-4f01-bc41-216f5865fd34)
10. ** Áp dụng thuật toán watershed để phân vùng các nhãn đã gán, ranh giới giữa các vùng
![image](https://github.com/user-attachments/assets/bdebccb8-90b8-4dad-9e2a-1dae321c9a71)
11. ** Chuyển về ảnh để hiển thị
![image](https://github.com/user-attachments/assets/5a8c9aa0-0bd8-4bd5-9bb4-4e3a3c43c3dc)

# Biến đổi đối tượng trong ảnh
Dilation cho phép các pixel ở foreground của 1 ảnh có thể соco giãn.

# Giải thích cách hoạt động
# Sử dụng binary_dilation
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/18d3ab3d-b0c3-4469-9414-896cec5cb291)
2. ** Đọc ảnh từ file - chuyển về ảnh xám màu - Áp dụng phép giãn nhị phân lên ảnh data với 50 lần lặp
![image](https://github.com/user-attachments/assets/e9a82305-9147-44eb-a49d-85135fea6aa1)
3. ** Chuyển về ảnh để hiển thị
![image](https://github.com/user-attachments/assets/41ce4acd-e924-4ec2-ad66-d7fc73c07202)

# Sử dụng binary_opening
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/18d3ab3d-b0c3-4469-9414-896cec5cb291)
2. ** Đọc ảnh từ file - chuyển về ảnh xám màu
![image](https://github.com/user-attachments/assets/f761255f-1911-409d-935a-453de0f746ec)
3. ** Áp dụng phép giãn nhị phân lên ảnh data với 25 lần lặp
4. ** Tạo phần tử cấu trúc
![image](https://github.com/user-attachments/assets/7eba7858-76c6-4450-a966-d88368adc17f)
5. ** Chuyển về ảnh để hiển thị
![image](https://github.com/user-attachments/assets/9c30529f-4747-4ab0-9fe0-e7e65717899a)

# Sử dụng binary_erosion
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/e67c0248-b286-438c-b017-0a85c775f073)
2. ** Đọc ảnh từ file - chuyển về ảnh xám màu
![image](https://github.com/user-attachments/assets/88c26827-4d14-43f9-b5d4-263413107f38)
3. ** Áp dụng phép xói mòn nhị phân lên ảnh data với 50 lần lặp
4. ** Tạo phần tử cấu trúc
![image](https://github.com/user-attachments/assets/8e97912d-19fa-450d-88aa-3e6c39e6236f)
5. ** Chuyển về ảnh và hiển thị
![image](https://github.com/user-attachments/assets/2c132a55-4ac6-4ec1-a2e7-8fc9e834f53c)

# Sử dụng binary_closing
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/eb5c3482-f7b6-4443-ac25-19074b7780b1)
2. ** Đọc ảnh từ file - chuyển về ảnh xám màu
![image](https://github.com/user-attachments/assets/bedc0610-f842-4be3-af92-f91e69a4b15f)
3. ** Áp dụng phép đóng nhị phân lên ảnh với 50 lần lặp
4. ** Tạo phần tử cấu trúc
![image](https://github.com/user-attachments/assets/0d4900d2-726b-4c14-b96a-c406be05a884)
5. ** Chuyển về ảnh và hiển thị
![image](https://github.com/user-attachments/assets/66e5d47e-fb79-4475-aac9-0d0d16382a3d)

# bài tập 2
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/570e9f72-2204-462c-8929-7c17394e1d42)
2. ** Đọc ảnh từ file - chuyển về ảnh xám màu - Chuyển ảnh về dạng numpy
![image](https://github.com/user-attachments/assets/bfa71e26-9336-4fa9-b397-d0eb3d6d5572)
3. **  Chọn vùng ảnh - Sử dụng rotate để xoay ảnh góc 45 độ
![image](https://github.com/user-attachments/assets/0b773847-bf79-4545-baa9-9af56f18995b)
4. ** Sử dụng adaptive thresholding cho từng vùng 61x61 pixel trên ảnh đã xoay
5. ** So sánh từng pixel để tạo ảnh nhị phân
![image](https://github.com/user-attachments/assets/ce5ad040-4f29-4d71-92e0-6a604d660cf4)
6. ** Lưu ảnh ra file - chuyển về ảnh và hiển thị ( vì là ảnh xám màu nên phải chuyển về dạng unit 8 )
![image](https://github.com/user-attachments/assets/210ac94b-f0d6-4d1e-a2f5-dd0b1a7f6307)
![image](https://github.com/user-attachments/assets/834e4380-d20b-4430-980f-3229692c6e92)

# Bài tập 1
1. ** Import thư viện
![image](https://github.com/user-attachments/assets/166e972e-6912-42bc-89bd-05682389ee9b)
2. ** Đọc ảnh từ file - chuyển về ảnh xám màu - chuyển ảnh về dạng numpy
![image](https://github.com/user-attachments/assets/7d698c63-4cbd-4998-b010-2181e9d5e148)
4. ** Chọn vùng ảnh
![image](https://github.com/user-attachments/assets/a5fb27b7-ec8b-472c-8cfa-a8149441c11a)
5. ** Tịnh tiến ảnh sang phải 100px
![image](https://github.com/user-attachments/assets/d2255556-4bfb-444a-9469-154906e74c37)
6. ** Tính ngưỡng otsu trên vùng ảnh được làm tối đi 0.3 lần
7. ** So sánh pixel nào trên canvas lớn hơn ngưỡng otsu sẽ lấy
![image](https://github.com/user-attachments/assets/a0761e7d-bf17-4fcd-b8c4-2ff8d46f729e)
8. ** Lưu ảnh ra file - chuyển về ảnh và hiển thị ( vì là ảnh xám màu nên phải chuyển về dạng unit 8 )

![image](https://github.com/user-attachments/assets/3afc9c25-3df1-4d2a-a2cf-a63225fa7072)






























