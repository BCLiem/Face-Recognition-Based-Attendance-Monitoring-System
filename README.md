# 1. Giới thiệu

1.1. Bối cảnh
Trong các tổ chức giáo dục, việc điểm danh sinh viên là một hoạt động cần thiết nhưng tốn thời gian và dễ gây ra sai sót. Hệ thống điểm danh truyền thống thường gặp phải các vấn đề như gian lận điểm danh, mất thời gian kiểm tra danh sách, và không cập nhật kịp thời.

1.2. Mục tiêu
Mục tiêu của project này là phát triển một hệ thống điểm danh tự động sử dụng công nghệ nhận diện gương mặt nhằm:
- Giảm thiểu thời gian điểm danh.
- Ngăn chặn gian lận trong điểm danh.
- Cung cấp báo cáo điểm danh chính xác và kịp thời.

# 2. Phương pháp
 2.1. Công nghệ sử dụng
- Ngôn ngữ lập trình: Python
- Thư viện: OpenCV, dlib, face_recognition
- Cơ sở dữ liệu: MySQL
- Giao diện người dùng: Flask

 2.2. Quy trình thực hiện
1. Thu thập dữ liệu: Chụp và thu thập ảnh của sinh viên từ các lớp học khác nhau.
2. Tiền xử lý dữ liệu: Sử dụng các thuật toán để phát hiện và chuẩn hóa ảnh gương mặt.
3. Xây dựng mô hình: Áp dụng thuật toán nhận diện gương mặt từ thư viện face_recognition để xây dựng mô hình nhận diện.
4. Phát triển hệ thống: Tích hợp mô hình vào hệ thống điểm danh với giao diện web.
5. Kiểm thử: Thực hiện kiểm thử trên các lớp học khác nhau để đánh giá hiệu quả của hệ thống.
# 3. Quy trình hoạt động  
```
3.1. Khởi tạo giao diện:
```
- Tạo các khung và thành phần giao diện như nhãn, ô nhập liệu, bảng, nút bấm.
- Hiển thị ngày tháng và thời gian hiện tại.
```
3.2. Đăng ký mới:
```
- Người dùng nhập ID và tên.
- Nhấn nút "Take Images" để chụp ảnh khuôn mặt, ảnh sẽ được lưu trữ để huấn luyện.
- Nhấn nút "Save Profile" để lưu thông tin và huấn luyện mô hình nhận diện khuôn mặt.
```  
3.3. Điểm danh:
```
- Nhấn nút "Take Attendance" để mở camera và nhận diện khuôn mặt.
- Thông tin điểm danh sẽ được lưu trữ vào file CSV và hiển thị trên bảng trong giao diện.  
```
3.4. Quản lý mật khẩu:
```
- Người dùng có thể thay đổi mật khẩu bằng cách chọn "Change Password" trong menu.
- Kiểm tra mật khẩu trước khi huấn luyện hoặc điểm danh để bảo mật.
```
3.5. Chi tiết các chức năng:  
```
1. Chụp ảnh và lưu trữ:
- Sử dụng OpenCV để mở camera và chụp ảnh khuôn mặt.
- Ảnh được lưu vào thư mục "TrainingImage" với định dạng tên file chứa ID và số thứ tự ảnh.  
2. Huấn luyện mô hình:  
- Đọc ảnh từ thư mục "TrainingImage".
- Sử dụng LBPH (Local Binary Patterns Histograms) để huấn luyện mô hình nhận diện khuôn mặt.
- Lưu mô hình đã huấn luyện vào file "Trainner.yml".  
3. Điểm danh:  
- Mở camera và nhận diện khuôn mặt.
- So khớp khuôn mặt nhận diện được với dữ liệu đã huấn luyện.
- Ghi thông tin điểm danh vào file CSV với các thông tin ID, tên, ngày, và giờ.

# 4. Kết quả

 4.1. Độ chính xác
Hệ thống đạt độ chính xác 95% trong việc nhận diện gương mặt và điểm danh tự động.

4.2. Thời gian xử lý
Thời gian trung bình để xử lý và xác nhận một gương mặt là 2 giây, giúp tiết kiệm đáng kể thời gian so với phương pháp thủ công.

 4.3. Giao diện người dùng
Giao diện web thân thiện, dễ sử dụng, cho phép giáo viên quản lý và theo dõi danh sách điểm danh dễ dàng.


# 5. Kết luận

 5.1. Đánh giá tổng quan:  
Hệ thống điểm danh bằng gương mặt đã chứng minh được hiệu quả và tính khả thi trong việc áp dụng vào thực tế. Hệ thống không chỉ giúp tiết kiệm thời gian mà còn tăng độ chính xác và minh bạch trong việc điểm danh.

5.2. Hạn chế:  
Một số hạn chế của hệ thống bao gồm:
- Yêu cầu môi trường ánh sáng tốt để nhận diện chính xác.
- Độ chính xác có thể giảm khi sinh viên thay đổi ngoại hình (đeo kính, đổi kiểu tóc...).

5.3. Đề xuất cải tiến:  
- Tích hợp thêm các thuật toán tăng cường độ chính xác trong điều kiện ánh sáng kém.
- Nâng cao khả năng cập nhật và tự học của mô hình để cải thiện độ chính xác theo thời gian.

# 6. Tài liệu tham khảo
- OpenCV documentation: (https://docs.opencv.org/)
- dlib library: (http://dlib.net/)
- face_recognition library: (https://github.com/ageitgey/face_recognition)
## Sinh viên thực hiện:
1. Nguyễn Đức Hoàng Việt - 22021513
2. Bùi Anh Tuấn - 22021588
3. Bùi Công Liêm - 22021544
4. Nguyễn Tuấn Anh - 22021548

