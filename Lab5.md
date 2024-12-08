
# Payroll System - Subsystem Design

## 1. Subsystem: PaymentProcessing
### Mục tiêu
Xử lý thanh toán lương nhân viên, bao gồm giao tiếp với ngân hàng và xác nhận thanh toán.

### Thành phần chính
- **`PayrollController`**: Điều phối toàn bộ quy trình xử lý lương.
- **`IBankSystem`**: Interface giao tiếp với hệ thống ngân hàng, đảm bảo tính trừu tượng hóa.
- **`BankSystem`**: Thực hiện chi tiết các tác vụ giao tiếp với ngân hàng.
- **`Paycheck`**: Đối tượng chứa thông tin chi tiết về lương của nhân viên.
- **`BankInformation`**: Lưu thông tin tài khoản ngân hàng của nhân viên.

### Luồng hoạt động
1. **Input**: `PayrollController` nhận danh sách nhân viên và thông tin lương.
2. `PayrollController` sử dụng `IBankSystem` để gửi yêu cầu thanh toán cho từng nhân viên.
3. `BankSystem` xử lý giao dịch với ngân hàng và trả về kết quả.
4. **Output**: Thông báo thành công/thất bại cho từng giao dịch.

### Diagram

![](https://www.planttext.com/api/plantuml/png/j98xRiCm38PtduB8r0pD0OGW2D8i1eh0W4z0gunhM0z3Zy5eSx8EFLAlK5bn7BbrnseXHFxwz8lKryVdtZeqpakHTSXRh0bM1VQIb2kCvcHjeseeVMLxwqYku2s3iBX0Qo48ZHRYIIitH39ZDQxkUdpKF7JOyrVYhMNmt5YtBSRzRXsFNB8O6kN8d94Jv0TKRHalNQOE5YSgWnjlpU2WjI1KAVVgzn-GDqqAHAczSWoEsbU2xdcIdT0zKNvaK3eJ6dklLS5QhixQI7IDLYnwJHBBZqa4CmES3mvENbPabkyweQHPPMJ_7kdZRZOB1jwIZTeqlNtVR9B-_iKAiAbZ36fIPD2DkAamg7w-ZW4F66oKpIxPdjJBy6E_0G00__y30000)

---

## 2. Subsystem: PayslipPrinting
### Mục tiêu
In phiếu lương nhân viên trên máy in được chỉ định.

### Thành phần chính
- **`PayrollController`**: Điều phối việc in phiếu lương.
- **`IPrintService`**: Interface trừu tượng hóa giao tiếp với máy in.
- **`PrintService`**: Quản lý các thao tác thực tế trên máy in.
- **`Paycheck`**: Đối tượng chứa dữ liệu cần in.

### Luồng hoạt động
1. **Input**: `PayrollController` nhận danh sách các phiếu lương cần in.
2. `PayrollController` gọi `IPrintService` để thực hiện thao tác in.
3. `PrintService` giao tiếp với máy in và hoàn thành nhiệm vụ.
4. **Output**: Phiếu lương được in.

### Diagram

![](https://www.planttext.com/api/plantuml/png/h95BQWCn38RtSmgHLRDe3c1226atXL06vWIAgqnD_CAo2qERatMH8-KAzHWtdQHqLss4f5-V9FlyULfpn12JqOr7US2UODRYm5hvDYWRbUsXIpiUE9APmNi3sQH6PiYouBH-S3QEdaAj5lDZSmNndST1lf8yi82juhXiQxoQbuvZKrpkeB17IV1KPdSKtbIERh4Nd81lq5p0nZbDQAV0kkT_igfcoa7Zaeq27btQQVh9a_7Q3KJFQ4X05_EuVahy_NxtgvlB1IGcBkhhml9ZiRWwx2zYHbvs5j2JfO0n8u_DckpB-ErV0000__y30000)


---

## 3. Subsystem: ProjectManagement
### Mục tiêu
Quản lý thông tin dự án, bao gồm mã dự án và thẻ thời gian của nhân viên.

### Thành phần chính
- **`TimecardController`**: Điều phối các thao tác liên quan đến thẻ thời gian.
- **`IProjectManagementDatabase`**: Interface giao tiếp với cơ sở dữ liệu dự án.
- **`ProjectManagementDatabase`**: Quản lý dữ liệu thực tế của dự án.
- **`ChargeNumList`**: Danh sách mã dự án được sử dụng để phân bổ chi phí.

### Luồng hoạt động
1. **Input**: `TimecardController` nhận thông tin thẻ thời gian từ nhân viên hoặc quản lý.
2. `TimecardController` sử dụng `IProjectManagementDatabase` để truy vấn/cập nhật thông tin.
3. `ProjectManagementDatabase` thực hiện các thao tác cần thiết trên cơ sở dữ liệu.
4. **Output**: Thông tin dự án hoặc xác nhận cập nhật thành công.

### Diagram

![](https://www.planttext.com/api/plantuml/png/p99DRW8n38NtSmgB5KY50qG8eS86gKL8z08cuqw7vcSKEvLGoycww95wXGw1cKvLG5tMcoY9t_CNEv_l7rCM31AjoIhKprWGz5R1RqdBFRfwQya9hEE6TonaU_2QGHtQ83Cyb9OqXdpcdGHl38NJTGgRz4qEzybMnk-85dC5QmcbAsv0Fs4eQ1bjSpH8-dsMbj89XKVK18jVJ7CKt21Jjs91CciCkJzGS5UoZ8_6a--qMEKeBTWVkHJSUcy8NHVms8R_pDRMF9JhyhGkV0RbP75cliF9jLaeY4oSj5Uonc-ZqUMc9VLbyR0c-Fae1O5gTdgfA--pARdyy9k_0000__y30000)


---

## 4. Subsystem: UserManagement
### Mục tiêu
Quản lý thông tin nhân viên và quyền truy cập hệ thống.

### Thành phần chính
- **`UserController`**: Điều phối các hoạt động quản lý người dùng.
- **`IUserDatabase`**: Interface giao tiếp với cơ sở dữ liệu nhân viên.
- **`UserDatabase`**: Lưu trữ thông tin chi tiết của nhân viên, bao gồm dữ liệu cá nhân và quyền truy cập.

### Luồng hoạt động
1. **Input**: `UserController` nhận yêu cầu tạo, sửa, hoặc xóa người dùng.
2. `UserController` sử dụng `IUserDatabase` để thực hiện các thao tác trên dữ liệu.
3. **Output**: Kết quả thành công/thất bại của các thao tác.

### Diagram

![](https://www.planttext.com/api/plantuml/png/p58nZi8m4EpzYXNLKS03h1D2G4D1XNZ0aYmHmdOYxmRfTF0o2fx45x0jf2GGYOQ2BMnhTZmUhUTskKvPq4jjZQemEs11CDWm-HMwSBRa1DRrblzOo0xWNq6ep20pHDQyTE9BOyW_MgaoJoWK-pzrM7IY3ZNCoj8GkeQOaw4MSRdGi1Q_TqKVkQxojwfdbRQz4_8xp0YMaRH0mIqojJqo7Z_ki23fPqQqxQyPu1TRQrlgNcjmXvPUqP28BlhGVahCQFBqFJg-mudQRVoUnkFEk7hbWbxohS6cyB8wgocvF6Rx3W00__y30000)

---

## 5. Subsystem: ReportGeneration
### Mục tiêu
Tạo các báo cáo về lương, dự án, hoặc hoạt động nhân viên.

### Thành phần chính
- **`ReportController`**: Điều phối việc tạo báo cáo.
- **`IReportGenerator`**: Interface hỗ trợ tạo báo cáo ở các định dạng khác nhau.
- **`ReportGenerator`**: Xử lý logic tạo báo cáo cụ thể.
- **`Database`**: Cung cấp dữ liệu cần thiết.

### Luồng hoạt động
1. **Input**: `ReportController` nhận yêu cầu tạo báo cáo từ người dùng.
2. `ReportController` gọi `IReportGenerator` để xử lý yêu cầu.
3. `ReportGenerator` truy vấn dữ liệu từ cơ sở dữ liệu và tạo báo cáo.
4. **Output**: Báo cáo được xuất ra file hoặc gửi qua email.

# Diagram

![](https://www.planttext.com/api/plantuml/png/p58nZi8m4EpzYXNLKS03h1D2G4D1XNZ0aYmHmdOYxmRfTF0o2fx45x0jf2GGYOQ2BMnhTZmUhUTskKvPq4jjZQemEs11CDWm-HMwSBRa1DRrblzOo0xWNq6ep20pHDQyTE9BOyW_MgaoJoWK-pzrM7IY3ZNCoj8GkeQOaw4MSRdGi1Q_TqKVkQxojwfdbRQz4_8xp0YMaRH0mIqojJqo7Z_ki23fPqQqxQyPu1TRQrlgNcjmXvPUqP28BlhGVahCQFBqFJg-mudQRVoUnkFEk7hbWbxohS6cyB8wgocvF6Rx3W00__y30000)


---

## Kết luận
Việc thiết kế hệ thống Payroll System với các subsystem phân tách như trên giúp:
- **Dễ bảo trì:** Các chức năng được chia nhỏ, dễ sửa đổi khi có yêu cầu mới.
- **Tính mở rộng:** Có thể bổ sung thêm subsystem mà không ảnh hưởng đến các phần khác.
- **Tăng hiệu quả:** Quy trình xử lý rõ ràng, giảm thiểu lỗi trong giao tiếp giữa các thành phần.
