# **BÁO CÁO CUỐI KỲ**
## *Đề tài: iLearn: A digital learning environment*

### 1.Mô tả tóm tắt bài toán
**Sự cần thiết và lợi ích khi giải quyết bài toán:**
* Hệ thống học tập kỹ thuật số Glow được triển khai tại Scotland từ năm 2006, nhưng hiện tại đã lỗi thời và không đáp ứng yêu cầu thực tế.
* Nhiều giáo viên và học sinh không sử dụng hệ thống vì tính phức tạp và thiếu hiệu quả, dẫn đến lãng phí nguồn lực.

**Việc phát triển hệ thống mới nhằm:**
* Hỗ trợ các công nghệ hiện đại để cải thiện trải nghiệm học tập.
* Đáp ứng nhu cầu của hơn 3000 trường học, 50,000 giáo viên, và 1 triệu học sinh.
* Tăng khả năng tương tác giữa phụ huynh và học sinh thông qua các thiết bị di động và trình duyệt web.

**Các yêu cầu chức năng:**
* Hỗ trợ truy cập đa nền tảng (desktop, laptop, thiết bị di động).
* Cung cấp môi trường mở để tích hợp dịch vụ web và ứng dụng bên thứ ba.
* Hỗ trợ chia sẻ nội dung học tập, tương tác thời gian thực giữa giáo viên và học sinh.
* Quản lý tài nguyên học tập và tổ chức lớp học trực tuyến.

**Các yêu cầu phi chức năng:**
* Khả năng mở rộng để phục vụ số lượng lớn người dùng.
* Bảo mật thông tin học sinh, giáo viên, và phụ huynh.
* Độ ổn định cao, đảm bảo hoạt động 24/7.
* Tính linh hoạt để đáp ứng các yêu cầu thay đổi trong tương lai.

### 2. Phân tích các ca sử dụng
### **Kiến trúc đề xuất:**
**Hệ thống được xây dựng trên kiến trúc đa tầng, gồm:**
* Tầng giao diện (Frontend): Hiển thị thông tin và cung cấp chức năng tương tác với người dùng.
* Tầng dịch vụ (Backend): Xử lý logic nghiệp vụ và quản lý tài nguyên.
* Tầng dữ liệu: Lưu trữ và quản lý cơ sở dữ liệu người dùng, tài nguyên học tập.
  
### **Các cơ chế phân tích**
**Xác thực và phân quyền:**
* Đảm bảo chỉ người dùng hợp lệ có thể truy cập vào hệ thống.
* Sử dụng Auth2 và mã hóa dữ liệu trong quá trình xác thực.
  
**Quản lý tài nguyên học tập:**
* Hỗ trợ tìm kiếm, chia sẻ và tải về tài liệu học tập.
  
**Tương tác thời gian thực:** 
* Tích hợp WebSocket để cập nhật thông tin lớp học theo thời gian thực.
  
![](https://www.plantuml.com/plantuml/png/TP6zIZD158RxlOf3-jp2HpuLGOYWYKhQSVOmMTmz6-P73PBAmagm5y4WDa8mbcQnsh3tCNVYxC4Ykz5cO8RtUNdEd9wnGbkNfP6GDjTmQb174o4lX4Be3AV6OjQ1cmX0exI2L8gmhtEoI34_0pY3KfYGNZ-iRqa1ZVrgCUc0CD3FLKBDq0WpiELp0gJSj7mZpfqbU3L0apijqJJp9zMocfCAp5n2wel72OnzSI-Psqs5CGTaKGVx9AU0pXggEs6INqn7TPaDFHyII5LBNpmb49UVfBZslxFZ9d3i_Eg582s_jkKF1Gc5V-YFVB5WhAr-fFCGDZp1blQUiE8yy6tlVhLqOBKltY6kZpJnnPtZlg7DDTPSw_kqcy9ri7-rMyW0hKxmaYbMc4Nr-g7R_VUpEJxvpb_IM1C_DofQss2mEUV6XVaDwnvIxBBq6m00)

**Kết quả phân tích từng ca sử dụng**
**Ca sử dụng 1:** Đăng nhập
* Mô tả: Người dùng nhập thông tin tài khoản để truy cập hệ thống.
* Biểu đồ:  
![](https://www.plantuml.com/plantuml/png/SoWkIImgAStDuKfCBialKWWjJYtYAYrEJKuiJbLGyijuk6jjWKB9uGMP2jaP-GztBSvJKaWiLl3CAoWjSIvAJKdDAybCp2b6w8Wul31PeIJZuUwDoPZQ74jBCa0waXDBKX5Qd3DAAn_kRivJo3YsuU7ksNdf2cM75-Gh0Cre1viqCIyTh3ieDIMpA3MvX0laHWLTNJjCPw0BW5IXsehC0SaYJ7L8pKi1XWC0)

**Ca sử dụng 2: Xem tài nguyên học tập**
* Mô tả: Người dùng duyệt và tải xuống tài nguyên học tập.
* Biểu đồ:  
![](https://www.plantuml.com/plantuml/png/SoWkIImgAStDuKfCBialKWWjJYtYAYrEJKuiJbLGyijuk6jjWKB9uGMP2jaP-GztBSvJKaWiLl3CAoWjSIvAJKdDAybCp2b6w8Wul31PeIJZuUwDoPZQ74jBCa0waXDBKX5Qd3DAAn_kRivJo3YsuU7ksNdf2cM75-Gh0Cre1viqCIyTh3ieDIMpA3MvX0laHWLTNJjCPw0BW5IXsehC0SaYJ7L8pKi1XWC0)

**Ca sử dụng 3: Tương tác lớp học**
* Mô tả: Giáo viên và học sinh tương tác qua các chức năng trực tuyến.
* Biểu đồ:  
![](https://www.plantuml.com/plantuml/png/POyn2i9044Nxd698doj8mFGMoGM6pS0kR6PXPwRm15v3iBQmtHGMdcHleeGqQldvlC_xlIXcjIKsw3Hbc0YTfxodKMqcriQ470f1U_G1GMfPGL_N037KzM8jeC3eCTEGd2rVmEHhkIM8LikTGNDT7mxKphKyUUDE70FJ4CIPI4ZSx0RGTOUVqTrcQ_wmddZ-t7W3)

### 3. Xác định các phần tử thiết kế
* Thành phần giao diện người dùng: Hỗ trợ hiển thị và thao tác thông qua trình duyệt và thiết bị di động.
* Thành phần backend: Quản lý logic nghiệp vụ và cung cấp API RESTful.
* Cơ sở dữ liệu: Lưu trữ thông tin người dùng, tài nguyên học tập và lịch sử tương tác.
* Cơ chế bảo mật: Bao gồm mã hóa dữ liệu, tường lửa ứng dụng và bảo vệ chống xâm nhập.

### 4. Thiết kế hệ thống con
Hệ thống được chia thành các hệ thống con chính:
1. Hệ thống con xác thực:  
* Xử lý đăng nhập, đăng ký và phân quyền.
2. Hệ thống con quản lý tài nguyên:  
* Lưu trữ, tìm kiếm và chia sẻ tài liệu học tập.
3. Hệ thống con tương tác:  
* Cung cấp chức năng lớp học trực tuyến, thảo luận và chia sẻ nội dung. 
### 5. Thiết kế các lớp
**Lớp User:**
* Thuộc tính: id, username, password, role
* Hành vi: login(), logout(), updateProfile()
**Lớp Resource:**
* Thuộc tính: id, title, content, author
* Hành vi: upload(), download(), search()
**Lớp ClassInteraction:**
* Thuộc tính: classId, teacherId, studentList
* Hành vi: shareDocument(), startDiscussion()

**Biểu đồ lớp:**  
![](https://www.plantuml.com/plantuml/png/PP51Ikn048RtEKKpg_UGkK0MCk1i11SYU82ckvmKTAh6gcfd8Pv6N7e11rUU93Un4u9fuoQ4huh-VkhVgNcntASc9A_gxXN4FJVEOMmTafM_N13v7bgd9aY7WevbzSGIAoISwesBn0UaV_zRzyGOPy3PQfAFqHlS2ZzWWf_1IpD7kGFbB05MSGpjboam6P1Ln6VhM2fGJ8bzhDsHJxHc2bv2DvA4QakGg_5xNIpYWo7J52XCS4a5FdGW2r3B4SXkK6r-RpHqNc3F8VTbLAkd5lQe8QiMGtsCgP7jzdAvH-isZtduU2MNlZutpJhUdsKTpkyk3kStEcoQ7L0iTNy3)
### 6. Kết luận
Hệ thống học tập kỹ thuật số mới được đề xuất nhằm giải quyết các hạn chế của hệ thống Glow hiện tại, đáp ứng nhu cầu ngày càng tăng của giáo dục số hóa. Với kiến trúc mở, khả năng mở rộng và tính bảo mật cao, hệ thống sẽ cải thiện hiệu quả học tập và tăng cường trải nghiệm người dùng. Trong tương lai, hệ thống có thể mở rộng để tích hợp trí tuệ nhân tạo và phân tích dữ liệu nhằm tối ưu hóa việc học tập và giảng dạy.
