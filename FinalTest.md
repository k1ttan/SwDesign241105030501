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
3. Xác định các phần tử thiết kế
Phần này trình bày các phần tử thiết kế sẽ xuất hiện trong hệ thống và cách tổ chức chúng, các cơ chế thiết kế sẽ được sử dụng trong hệ thống
4. Thiết kế hệ thống con
Phần này trình bày thiết kế chi tiết cho các hệ thống con đã đề xuất ở bước 3 bên trên.    
5. Thiết kế các lớp
Phần này trình bày chi tiết thiết kế của từng lớp trong hệ thống (thuộc tính, hành vi, …) và quan hệ giữa chúng với những phần tử khác trong hệ thống.
6. Kết luận
Phần này trình bày tóm tắt những vấn đề chính đã giải quyết trong bài toán, hướng mở rộng.
