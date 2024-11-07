## Phân tích các ca sử dụng trong hệ thống Payroll System
__Ca sử dụng chính trong hệ thống Payroll System bao gồm:__
* Login: Cho phép người dùng đăng nhập vào hệ thống.
* Maintain Employee Information: Quản trị viên Payroll có thể thêm, sửa, hoặc xóa thông tin nhân viên.
* Maintain Purchase Order: Nhân viên theo doanh số có thể tạo và duy trì thông tin đơn hàng để nhận hoa hồng.
* Maintain Timecard: Nhân viên cập nhật và nộp thông tin bảng chấm công cho tuần hiện tại.
* Run Payroll: Hệ thống tự động tính lương và tạo các khoản thanh toán cho nhân viên vào các ngày được quy định.
* Select Payment Method: Nhân viên chọn phương thức nhận lương.
* Create Employee Report: Nhân viên có thể tạo báo cáo như "Tổng số giờ làm việc" hoặc "Tổng tiền lương tính đến hiện tại".
* Create Administrative Report: Quản trị viên Payroll tạo các báo cáo quản lý như "Tổng số giờ làm" hoặc "Tổng tiền lương tính đến hiện tại".

## Code Java mô phỏng ca sử dụng "Maintain Timecard"
```
import java.util.HashMap;
import java.util.Map;

class Timecard {
    private String employeeId;
    private Map<String, Integer> hoursWorked; // Key: chargeNumber, Value: hours worked
    private boolean submitted;

    public Timecard(String employeeId) {
        this.employeeId = employeeId;
        this.hoursWorked = new HashMap<>();
        this.submitted = false;
    }

    public void addHours(String chargeNumber, int hours) {
        if (submitted) {
            System.out.println("Cannot modify a submitted timecard.");
            return;
        }
        if (hours < 0 || hours > 24) {
            System.out.println("Invalid hours. Please enter a valid number between 0 and 24.");
            return;
        }
        hoursWorked.put(chargeNumber, hoursWorked.getOrDefault(chargeNumber, 0) + hours);
    }

    public void submitTimecard() {
        this.submitted = true;
        System.out.println("Timecard submitted successfully.");
    }

    public void displayTimecard() {
        System.out.println("Timecard for Employee ID: " + employeeId);
        for (String chargeNumber : hoursWorked.keySet()) {
            System.out.println("Charge Number: " + chargeNumber + ", Hours: " + hoursWorked.get(chargeNumber));
        }
        System.out.println("Status: " + (submitted ? "Submitted" : "Not Submitted"));
    }
}

public class PayrollSystem {
    public static void main(String[] args) {
        Timecard timecard = new Timecard("EMP123");

        timecard.addHours("CHG001", 8);
        timecard.addHours("CHG002", 4);

        timecard.displayTimecard();

        timecard.submitTimecard();
        timecard.displayTimecard();

        timecard.addHours("CHG003", 6); // thử thay đổi sau khi đã nộp
    }
} 
```
