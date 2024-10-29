# 1. Phân tích kiến trúc
Đề xuất sử dụng kiến trúc client-server, trong đó hệ thống có giao diện desktop cho nhân viên, và máy chủ sẽ chịu trách nhiệm xử lý các logic nghiệp vụ cũng như truy cập cơ sở dữ liệu (CSDL) liên quan đến hệ thống quản lý dự án và hệ thống trả lương.
Lý do lựa chọn: Kiến trúc này giúp đảm bảo bảo mật và xử lý dữ liệu tập trung, đồng thời cho phép nhân viên truy cập từ nhiều nơi một cách linh hoạt và phân quyền hợp lý.

### Các thành phần kiến trúc:

* **Ứng dụng Client:** Là ứng dụng desktop mà nhân viên sẽ sử dụng để nhập dữ liệu (như thời gian làm việc) và lựa chọn phương thức thanh toán.
* **Máy chủ:** Đảm nhiệm các nghiệp vụ xử lý chính như tính toán tiền lương, và truy cập CSDL dự án cho các thông tin liên quan.
* **CSDL:** Gồm CSDL cũ (quản lý dự án) và CSDL mới cho dữ liệu trả lương và các thông tin nhân viên.
Biểu đồ Package UML mô tả kiến trúc:

![](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWjB3tIloqXLI7kvU2gISSp9JyqgK5Agv580WsZqpCLyX9VFXxlOyXRpqOniUxfwRgP1oU6TUUYnNBHV23D_32oiLaZCUxbuErnhnSFTQXPp3Uu7wCa0652YK0Qs8XKY659K2rJ_SjRP0mJdOnGVLC908t1WGHo6mzE6knNbWqu3ktAXmU65UB99qI15GMY7ds8PZ2w4Em-Tm1LrTEzpEmoK1qONXRWmHY3hShiQd0SqV3gbvAQ2OuW80003__mC0)
# 2. Cơ chế phân tích
* **Cơ chế lưu trữ (Persistency):** 
Sử dụng RDBMS để tích hợp với hệ thống quản lý dự án cũ, đảm bảo dữ liệu được lưu trữ và truy xuất hiệu quả.
* **Cơ chế bảo mật (Security):** 
Cơ chế kiểm soát truy cập nhằm giới hạn nhân viên và quản trị viên có quyền truy cập dữ liệu cụ thể (như bảng chấm công).
* **Tích hợp hệ thống cũ (Legacy Integration):** 
Sử dụng JDBC để kết nối với hệ thống CSDL quản lý dự án cũ nhằm lấy các mã dự án và chi tiết.
* **Tự động hóa (Automation):**
Thiết lập các tiến trình chạy tự động để thực hiện các tính toán lương vào các ngày cố định trong tháng.
# 3. Phân tích ca sử dụng Payment
**Các lớp phân tích:** Xác định các lớp NhanVien, PhuongThucThanhToan, và NganHang.
**Biểu đồ Sequence UML:**

![](https://www.planttext.com/api/plantuml/png/V94nQiCm58PtdUBXFHV8K09E28MqIzhILL549N2UX2qNV89ElKEL9IGGoD2f7Ze8V0-Ve5Veins7UCcYXtZ___s_q5_vEyaSJrs-IHWNpgGGFQgmHNZHuO0Hy0nc6vkOGafcIQU5jXmTH7FD3QnrNNuWn8cMw5hny_rGzX1y0KBLvQvTBsNwBjEX95vE5-rooXrVyKmoraV2w8w8C8QO29y8LbMdokCREBhl1GsE2fm97XdfIDq5a6DUbqSDHJZa8EgVNNiUBQ2YuMw2pWY2zOK8jwXEEQd2T-FHjvjSRAFhGg_1YouU8JdJliWZ6kObj7_mKnUr2juCcmzS4udhvkV-0G00__y30000)

**Biểu đồ lớp UML:**

![](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bToJc9niO9VHc9UM6Pgda8rbm8859SKPUQbAvIavg7mSnFzmY02oHdvUG4PfVbvwI4PfSaXGEqP8Vc9UHgQNBLSK3EnIACPdvEVc1aGWYAKd94PafbQWZ35BpqnpoCHA8FXCfWCYdXnVaXYfdS6q2wG4N1lAHagAUZgse5fBExYmkPMP3rmLrWfv6GUNfMdaFrmr_uIBeVKl1HG8080003__mC0)


# 4. Phân tích ca sử dụng Maintain Timecard
**Các lớp phân tích:** Xác định các lớp NhanVien, BangChamCong, và DuAn.

**Biểu đồ Sequence UML:**

![](https://www.planttext.com/api/plantuml/png/T951IWCn58RtESNFx7i15r9efGYrczhYDis49f3933EPGa_WAOIE889GTE6gMRW8U8-Sm2kOH4SSmMt-xt_VU-J3leqRGslJ5efGPieQsKAuUusrT4yw0srmKLIgt7DEgi199Ykg3RAPf2LowUsjnaH9has2LvT3xCfrUp3XxMEAbxpUyNg8J9RJUGgdrD0DRJWXlHAZyp0HPrW8VpfMs0RV7PGx5DX5DICX3SpNsC3Dl3rAvDu-GqMWZUxJGm7cNlMMV7EXqRj2P_x-qlvV-G57lpqthcFGSIaD5Vj6k8CMVpJzzjSYFcFZkX8i7PAgPjWQSvt7R_W4003__mC0)

**Biểu đồ lớp UML:**

![](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bToJc9niO9VHc9UM6Pgda8rbm8859SKPUQbAvIavg7mSnFzmY02oHc9kSxvUUaQcborN513d1BpqfsXuZ23KX9BKXNoqXChVH9pWHOaGqGpyqeKqZFpKSJWLhYKEkOX30Nnq5m5LOBcK9Wsk5UK39KKT7Nj59Iqb52SneNYJf0iM1LGDTW8XzIy553000000F__0m00)

# 5. Hợp nhất kết quả phân tích
* **Tích hợp:** Kết hợp các mô hình từ ca sử dụng Payment và Maintain Timecard để đảm bảo tính thống nhất và thể hiện các tương tác của nhân viên trong hệ thống trả lương một cách liền mạch.
* **Tài liệu cuối:** Tập hợp các biểu đồ package, sequence và class đã xây dựng vào tài liệu phân tích hoàn chỉnh.
