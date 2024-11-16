# Phân tích ca sử dụng Create Employee Report
  ## Các lớp phân tích
 - Boundary
  
EmployeeReportForm: Cung cấp giao diện cho Employee để nhập các tiêu chí tạo báo cáo (loại báo cáo, ngày bắt đầu, ngày kết thúc). Hiển thị báo cáo sau khi được tạo và cho phép Employee chọn lưu báo cáo nếu cần.

ProjectManagementDatabase: Tương tác với cơ sở dữ liệu để lấy danh sách số charge của các dự án, cần thiết khi Employee chọn báo cáo "Total Hours Worked for a Project".

  - Control

EmployeeReportController: Điều phối logic nghiệp vụ của ca sử dụng, xử lý yêu cầu tạo báo cáo từ Employee. Nhận các tiêu chí đầu vào, xác minh thông tin, và tạo báo cáo dựa trên các tiêu chí này. Khi Employee yêu cầu lưu báo cáo, lớp này sẽ tương tác với hệ thống lưu trữ để lưu báo cáo.

  - Entity

EmployeeReport: Đại diện cho báo cáo được tạo, bao gồm các thuộc tính như loại báo cáo, khoảng thời gian, và thông tin chi tiết khác (như số charge nếu có).

  ## Nhiệm vụ của từng lớp

  - Boundary
  
EmployeeReportForm: Hiển thị biểu mẫu cho Employee để nhập các tiêu chí tạo báo cáo. Sau khi nhận tiêu chí, gửi dữ liệu đến EmployeeReportController để tạo báo cáo, hiển thị báo cáo đã được tạo, và cung cấp tùy chọn lưu báo cáo.

ProjectManagementDatabase: Cung cấp danh sách số charge của các dự án khi Employee chọn báo cáo "Total Hours Worked for a Project".


  - Control

EmployeeReportController: Xử lý nghiệp vụ cho yêu cầu tạo báo cáo của Employee, bao gồm:
Nhận các tiêu chí từ EmployeeReportForm.
Kiểm tra tính hợp lệ của dữ liệu đầu vào.
Tạo đối tượng EmployeeReport với các thông tin cần thiết.
Nếu Employee yêu cầu lưu báo cáo, gửi yêu cầu đến hệ thống lưu trữ.


  - Entity

EmployeeReport: Đối tượng đại diện cho báo cáo của Employee với các thuộc tính như:
reportType: Loại báo cáo (Tổng số giờ làm việc, Tổng giờ làm việc cho dự án, Ngày nghỉ phép/ốm, hoặc Tổng tiền lương đến thời điểm hiện tại).
beginDate và endDate: Khoảng thời gian của báo cáo.
chargeNumber (nếu có): Số charge dự án khi báo cáo là "Total Hours Worked for a Project".
content: Nội dung của báo cáo đã được tạo dựa trên tiêu chí.

  ## Sequence Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/f9J1JiCm38RlUGgBC_00713I1e834c98dBtKwm9fCXmNj6VZm2Fn2ZXTMqRLZGbwMBl4_nVdjvFFzu-B9CXILzwWbSXmMQryN1EPUQn3WRpkH-vf5Lck8bV6nY0S_M1giXdrn8Q2E1bAJO62Sqm4TnoVoCej1Yofqk1fEsECwZp1Z5vg2fPWwh1ahE049amer2EXPPf-uEHy95Kuqq1b9G69O3SCtaX7ehSOgfowjFAuRkDLxOJO8Ioo1x-kUnaqkjFAUaN7K3IhOoZrcyIUcbzo6Fggr1c5OfYGGIzmiu2ZXoZeuJhMdE0nyZCLELV0pl0Z0_hifElAEolJ62diw9N0Bf5BWb1NS-BKC7Vhzcz7cJM7CUA-B4VzxggrXxLJEoElsV-KZcHnQ7rIWrFtVm9rQbZnVVjIscIxOI7EiyVmvcJvNVi_-rHI8CQSPNiUkZRgtRBB61EbV78IQjrbsP-TWrpTEdcDVaHxkA_V07qrt7yrypPFy-kkfdyri_vPEDr9tkpVUhWZj8bbK678f-wwWy8bYrpaqTnC5_gRx-ul0000__y30000)

  ## Class Diagram
   ![Diagram](https://www.planttext.com/api/plantuml/png/V591JiGm3Bpt5Jd2eUBU0rgfm0s4M3xWfgORb2R5TYjLY9Tnu4by0OTMrRBTaakL6MV67lVxysl70YHzwxFCUc0sjstduuZuX5qakOlKclVC_9xQSUTXJDZ5vOmrA5DbIKwG72pCN3sn2qhurYFB7WPKxEEyQnc3KFGUQV6sX21u8ZQ0TxN2AszM-QLsmsIMphMbT7qUEpI5sGkvqCnCXOqBDsgWHFhCC8Pw3Te3K8CFVLjfroSwLkV187_Xb5r0IkrFz76hZnHVqSez16YmLLATe0B69P0N57ieZqnvS_epAytpw-tC2yCw8clcKwpPPkLQHXzFg-B_NsqFMEX2D2KSaA_I96nqnP1bE-qf_QS_0000__y30000)

   . Giải thích biểu đồ lớp
   
EmployeeReportForm: Lớp boundary cho phép Employee nhập tiêu chí báo cáo, gửi thông tin đến EmployeeReportController, hiển thị báo cáo, và cung cấp tùy chọn lưu báo cáo.

EmployeeReportController: Điều phối logic nghiệp vụ của ca sử dụng, bao gồm xác minh tiêu chí, tạo đối tượng báo cáo EmployeeReport, và lưu trữ khi được yêu cầu.

EmployeeReport: Đại diện cho báo cáo của Employee với các thuộc tính cần thiết để tạo báo cáo theo tiêu chí.

ProjectManagementDatabase: Tương tác với cơ sở dữ liệu để lấy danh sách số charge khi cần và lưu báo cáo nếu Employee yêu cầu.


# Phân tích ca sử dụng Maintain Purchase Order
  ## Các lớp phân tích

  ## Nhiệm vụ của từng lớp

  ## Sequence Diagram
  
  ## Class Diagram


# Phân tích ca sử dụng Login
  ## Các lớp phân tích
- Boundary
  
LoginForm: Cung cấp giao diện cho người dùng nhập tên đăng nhập và mật khẩu, và hiển thị các thông báo lỗi nếu đăng nhập không thành công.

ProjectManagementDatabase: Tương tác với cơ sở dữ liệu quản lý dự án để xác minh thông tin đăng nhập của người dùng.

- Control
  
LoginController: Điều phối logic đăng nhập của hệ thống, bao gồm việc nhận và kiểm tra thông tin từ LoginForm và xác minh thông tin người dùng qua ProjectManagementDatabase.

- Entity
  
User: Đại diện cho tài khoản người dùng trong hệ thống, bao gồm các thuộc tính như tên đăng nhập, mật khẩu và các phương thức để xác minh thông tin.

  ## Nhiệm vụ của từng lớp
  - Boundary
    
LoginForm: Hiển thị giao diện đăng nhập, nhận tên đăng nhập và mật khẩu từ người dùng, gửi thông tin này đến LoginController để xác minh và hiển thị thông báo lỗi nếu đăng nhập không hợp lệ.

ProjectManagementDatabase: Kết nối với cơ sở dữ liệu để xác minh thông tin đăng nhập bằng cách kiểm tra tên đăng nhập và mật khẩu.

- Control
  
LoginController: Xử lý logic nghiệp vụ của quá trình đăng nhập. Nhận tên người dùng và mật khẩu từ LoginForm, gửi thông tin đến ProjectManagementDatabase để xác minh tính hợp lệ của tài khoản, và phản hồi đến LoginForm.

- Entity
  
User: Lưu trữ thông tin của người dùng, bao gồm các thuộc tính username và password.

  ## Sequence Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/f9BFIiD04CRlynJp0iLx3r8m2WK5iUXzkXd3olwfixkLF9i77ybNSDAqJQ0c8EOGoEptVVERoNv_VgrI9id5Eo2Je-1pOe5jBA4cQV4-DZRSHV5WOiWINL-vwJ-SIZbaczlULbEcBIN6HublRF831MhOgwGwdW2esZ5k-BrmC8oLfKR8uw8F1kY2S74zTCObteQinQ8dWJmZXHftbD97b1e6tSaqmAbrmogUSOx4wf_argGNSbO7v8cqQQlc7ePQuXDdiRpl8x3RrddSkSvgAn969Y2NSVrw9hawKQ1DkEyu0VMPHRfSrR7DuFzbGUE_KjcqSzIYwsgOYZ6S4h3J_7Kuf5m2_eFBXZ-JiOZUQAzOsaXlQWsmqdTtsNy0003__mC0).
  
  ## Class Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/Z991JWCn34NtEOMNHM8kC0jKKM15fKeL1p0PQmZA99NjeQegJiQ28t45ab5cfhIgH9R_-zjFTdw-lfUYoDfttXZhKGIUO-l2K-GEZWQ6rpZPUJnaRN5Jj9RqHOW3TdIgRLA7VUHcqahsaJdocaImfNDlsrkRdDdz_8EoYa4vUayy0NsWTmqg3VwYBnmrR9LTQ6zXLoX6vQHbXYvzAXYJC1OMVSpF-fJVS7mdgsiCYRMZe0-e-8f25t0hfYRv3hty1p7Dke_H4uOyR3v2LTrTxA46eT08s7c4EQ_9kUkmzOGfi7VwPgwNvaR3rch0uL0aPfd6vo_p2m00__y30000).

   . Giải thích biểu đồ lớp
     LoginForm: Hiển thị biểu mẫu đăng nhập và nhận thông tin đăng nhập từ người dùng, sau đó gửi đến LoginController. Nếu đăng nhập thành công, LoginForm sẽ hiển thị thông báo thành công; nếu không, hiển thị thông báo lỗi.
     
LoginController: Điều phối logic đăng nhập và tương tác với ProjectManagementDatabase để xác minh thông tin người dùng.

User: Đại diện cho thông tin của người dùng trong hệ thống, bao gồm username và password.

ProjectManagementDatabase: Kết nối với cơ sở dữ liệu và xác minh thông tin đăng nhập của người dùng.



# Phân tích ca sử dụng Create Adminstrative Report
  ## Các lớp phân tích
  Boundary: AdministrativeReportForm và ProjectManagementDatabase
  
  Control: AdministrativeReportController
  
  Entity: Report

  ## Nhiệm vụ của từng lớp
-AdministrativeReportForm:

Nhiệm vụ: Cung cấp giao diện để Payroll Administrator nhập các tiêu chí báo cáo, như loại báo cáo, khoảng thời gian, và danh sách nhân viên. Cũng hiển thị báo cáo sau khi được tạo và cho phép người dùng chọn lưu báo cáo nếu cần.


-ProjectManagementDatabase:

Nhiệm vụ: Cung cấp kết nối và truy xuất dữ liệu từ cơ sở dữ liệu, bao gồm lấy thông tin về nhân viên (như giờ làm việc hoặc lương) để sử dụng trong báo cáo. Đồng thời, lớp này hỗ trợ lưu báo cáo nếu Payroll Administrator chọn lưu.


-AdministrativeReportController:

Nhiệm vụ: Điều phối logic nghiệp vụ để tạo báo cáo dựa trên tiêu chí từ Payroll Administrator. Xử lý việc xác minh thông tin đầu vào, tạo đối tượng báo cáo và gửi yêu cầu lưu trữ đến ProjectManagementDatabase nếu cần.


-Report:

Nhiệm vụ: Đại diện cho đối tượng báo cáo, chứa các thuộc tính như loại báo cáo, ngày bắt đầu và kết thúc, danh sách nhân viên liên quan, và nội dung của báo cáo.

  ## Sequence Diagram
   ![Diagram](https://www.planttext.com/api/plantuml/png/f5HDJlCm4Dtx57C047iMYAg0n0Af-ZZ1r9wcW_oJpvw2SZOM78ahC6uQ2AXDY-YYJUrvRvxVlFZzzUsw26RP16_GIigmm2udxsSkSEGY6UiY5bZCp39jeiFSmMYJd-aVjIdBNSh1s1H5qNiBvlsUfsme2ai7_RfnABZ4Gh38wOciF634Xe8MtUnsZD5wJ_18_pSKBS4DOvCnm3dCCw7GZuO3irdCuFpge5our49bB0AImFPCkOSUn2YVibwgXD9wx7RrYcQXp0YhwiFHlhTHgmUiT2sTWTjsnzZeCuNMfuu88WOgPbBDjDVQwv6Y-obpB-C8LKzvQ1fAUKTYrryg7GcoLvte1UvNmB6weCmf0XS8N0h71ZH876tAMMaDwEUuY0aBLLzefVezDBZOSO_xR_iS7OToFREZII9rSVyWlYlkrvHpFiuJf6Kr4rvOrhyPmeJc8O0DHT9j6cRyEGKzjLsdLAZKU1VKzqBMdm4_oPVHwx75Zx1_Y-GNcVviUvmOYAbKZbbLyN2lz4SzY3j5h_vPiPwjcl3tv0viEwcLr1doPRYtm76nc5rThQ6xrkzwGNy0003__mC0)
  
  ## Class Diagram
 ![Diagram](https://www.planttext.com/api/plantuml/png/Z5BBJiD03BpdA_O8XuXxXAgY0YT0YF83RcB2Lli8jXifGdmP1pw9Ny1BLk7L0BciCkFCpepp-looP06IdNT5KJjWDYUDjy6o48ZjyGQxI78UoPl7mhm_ZUNEmP2mWyECjIZZv8gi85cOc3mziXDA-B13bZNqgDZJRtUlOX2ApY5D3cf24FmcsOEpZS8_733q7xFJLIEI9Kirb5vlXmvDPTP2DhIPsM1hmwaAAv6E36Deze2-St50l0AFhDI5PZaUrHPJKm4fsTHO6BvOkgQunLek8K2BNabLXWqmJi7lKEhxitn9OcT3pcwnB1T_rLmPrdIiDOzDxXNxD9yaSvrLtWt_vvlvl9NkGrl37lae9MEZcuMYMAglzAk-0G00__y30000)

 Giải thích biểu đồ lớp
 
AdministrativeReportForm: Lớp boundary hiển thị biểu mẫu cho Payroll Administrator nhập thông tin và tương tác với người dùng trong suốt quá trình tạo báo cáo. Gửi thông tin đầu vào đến AdministrativeReportController và hiển thị báo cáo sau khi được tạo.


AdministrativeReportController: Điều phối logic nghiệp vụ, bao gồm xác minh thông tin và tạo đối tượng Report. Khi Payroll Administrator yêu cầu lưu báo cáo, lớp này tương tác với ProjectManagementDatabase để thực hiện lưu trữ.


Report: Chứa các thông tin chính của báo cáo, như loại báo cáo và phạm vi ngày. Lớp này có thể bao gồm phương thức generateContent() để xây dựng nội dung báo cáo dựa trên tiêu chí đầu vào.


ProjectManagementDatabase: Cung cấp khả năng truy xuất và lưu trữ dữ liệu báo cáo, hỗ trợ lưu báo cáo khi Payroll Administrator chọn lưu trữ.


# Phân tích ca sử dụng Maintain Employee Info
  ## Các lớp phân tích

  ## Nhiệm vụ của từng lớp

  ## Sequence Diagram
  
  ## Class Diagram



# Phân tích ca sử dụng Run Payroll
  ## Các lớp phân tích

  ## Nhiệm vụ của từng lớp

  ## Sequence Diagram
  
  ## Class Diagram



# Code Java mô phỏng ca sử dụng Maintain Timecard

```java
package maintain;

import java.time.LocalDate;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;
import java.util.Scanner;

// Class đại diện cho timecard
class Timecard {
    private int employeeId;
    private LocalDate startDate;
    private LocalDate endDate;
    private LocalDate submittedDate;
    private boolean isSubmitted;
    private Map<Integer, Map<LocalDate, Double>> hoursPerChargeNumber; // Charge number -> Date -> hours
    private static final int MAX_HOURS_PER_DAY = 24;
    private static final int MAX_HOURS_PER_WEEK = 40;

    public Timecard(int employeeId) {
        this.employeeId = employeeId;
        this.startDate = LocalDate.now().minusDays(LocalDate.now().getDayOfWeek().getValue() - 1);
        this.endDate = startDate.plusDays(6);
        this.isSubmitted = false;
        this.hoursPerChargeNumber = new HashMap<>();
    }

    public boolean addHours(int chargeNumber, LocalDate date, double hours) {
        if (isSubmitted) {
            System.out.println("Timecard đã được submit, không thể thay đổi.");
            return false;
        }
        
        if (hours > MAX_HOURS_PER_DAY) {
            System.out.println("Số giờ làm việc trong ngày không thể vượt quá 24 giờ.");
            return false;
        }

        if (date.isBefore(startDate) || date.isAfter(endDate)) {
            System.out.println("Ngày không nằm trong khoảng thời gian của timecard.");
            return false;
        }

        // Tính tổng số giờ trong ngày
        double totalHoursForDay = hoursPerChargeNumber.values().stream()
            .mapToDouble(dateMap -> dateMap.getOrDefault(date, 0.0))
            .sum() + hours;

        if (totalHoursForDay > MAX_HOURS_PER_DAY) {
            System.out.println("Tổng số giờ làm việc trong ngày vượt quá 24 giờ.");
            return false;
        }

        hoursPerChargeNumber.computeIfAbsent(chargeNumber, k -> new HashMap<>())
                           .put(date, hours);
        return true;
    }

    public void displayTimecard() {
        System.out.println("\n=== Thông tin Timecard ===");
        System.out.println("Employee ID: " + employeeId);
        System.out.println("Thời gian: " + startDate + " đến " + endDate);
        System.out.println("Trạng thái: " + (isSubmitted ? "Đã gửi" : "Nháp"));
        if (isSubmitted) {
            System.out.println("Ngày gửi: " + submittedDate);
        }
        System.out.println("\nSố giờ làm việc:");
        hoursPerChargeNumber.forEach((chargeNumber, dateMap) -> {
            System.out.println("\nCharge Number: " + chargeNumber);
            dateMap.forEach((date, hours) -> 
                System.out.println(date + ": " + hours + " giờ"));
        });
    }

    public boolean submit() {
        if (isSubmitted) {
            System.out.println("Timecard đã được submit trước đó.");
            return false;
        }

        // Validate total hours per week
        double totalHours = hoursPerChargeNumber.values().stream()
            .flatMap(dateMap -> dateMap.values().stream())
            .mapToDouble(Double::doubleValue)
            .sum();

        if (totalHours > MAX_HOURS_PER_WEEK) {
            System.out.println("Tổng số giờ làm việc trong tuần vượt quá " + MAX_HOURS_PER_WEEK + " giờ.");
            return false;
        }

        this.submittedDate = LocalDate.now();
        this.isSubmitted = true;
        System.out.println("Timecard đã được gửi thành công.");
        return true;
    }

    public boolean isSubmitted() {
        return isSubmitted;
    }
}

// Class quản lý Project Management Database
class ProjectManagementDB {
    private boolean isAvailable;
    private List<Integer> chargeNumbers;

    public ProjectManagementDB() {
        this.isAvailable = true;
        this.chargeNumbers = new ArrayList<>(Arrays.asList(1001, 1002, 1003, 1004));
    }

    public List<Integer> getChargeNumbers() throws DatabaseUnavailableException {
        if (!isAvailable) {
            throw new DatabaseUnavailableException("Project Management Database không khả dụng.");
        }
        return new ArrayList<>(chargeNumbers);
    }

    public void setAvailable(boolean available) {
        this.isAvailable = available;
    }
}

class DatabaseUnavailableException extends Exception {
    public DatabaseUnavailableException(String message) {
        super(message);
    }
}

// Main class để demo với user input
public class Maintain {
    private static Scanner scanner = new Scanner(System.in);
    private static Map<Integer, Timecard> timecards = new HashMap<>();
    private static ProjectManagementDB projectDB = new ProjectManagementDB();

    public static void main(String[] args) {
        System.out.println("Chào mừng đến với Hệ thống Timecard");
        
        while (true) {
            try {
                System.out.println("\n=== Menu ===");
                System.out.println("1. Xem Timecard");
                System.out.println("2. Thêm Giờ");
                System.out.println("3. Gửi Timecard");
                System.out.println("4. Thoát");
                System.out.print("Chọn một tùy chọn: ");

                int choice = Integer.parseInt(scanner.nextLine());
                
                switch (choice) {
                    case 1:
                        viewTimecard();
                        break;
                    case 2:
                        addHours();
                        break;
                    case 3:
                        submitTimecard();
                        break;
                    case 4:
                        System.out.println("Tạm biệt!");
                        return;
                    default:
                        System.out.println("Tùy chọn không hợp lệ. Vui lòng thử lại.");
                }
            } catch (NumberFormatException e) {
                System.out.println("Vui lòng nhập một số hợp lệ.");
            }
        }
    }

    private static void viewTimecard() {
        System.out.print("Nhập Employee ID: ");
        int employeeId = Integer.parseInt(scanner.nextLine());
        
        Timecard timecard = timecards.get(employeeId);
        if (timecard == null) {
            System.out.println("Không tìm thấy timecard. Đang tạo timecard mới...");
            timecard = new Timecard(employeeId);
            timecards.put(employeeId, timecard);
        }
        
        timecard.displayTimecard();
    }

    private static void addHours() {
        System.out.print("Nhập Employee ID: ");
        int employeeId = Integer.parseInt(scanner.nextLine());
        
        Timecard timecard = timecards.computeIfAbsent(employeeId, Timecard::new);
        
        try {
            List<Integer> chargeNumbers = projectDB.getChargeNumbers();
            System.out.println("Các charge number có sẵn: " + chargeNumbers);
            
            System.out.print("Nhập charge number: ");
            int chargeNumber = Integer.parseInt(scanner.nextLine());
            
            System.out.print("Nhập ngày (YYYY-MM-DD): ");
            LocalDate date = LocalDate.parse(scanner.nextLine());
            
            System.out.print("Nhập số giờ làm việc: ");
            double hours = Double.parseDouble(scanner.nextLine());
            
            if (timecard.addHours(chargeNumber, date, hours)) {
                System.out.println("Giờ đã được thêm thành công.");
            }
        } catch (DatabaseUnavailableException e) {
            System.out.println(e.getMessage());
            System.out.print("Bạn có muốn tiếp tục mà không có charge numbers không? (y/n): ");
            if (scanner.nextLine().toLowerCase().equals("n")) {
                return;
            }
        }
    }

    private static void submitTimecard() {
        System.out.print("Nhập Employee ID: ");
        int employeeId = Integer.parseInt(scanner.nextLine());
        
        Timecard timecard = timecards.get(employeeId);
        if (timecard == null) {
            System.out.println("Không tìm thấy timecard cho nhân viên này.");
            return;
        }
        
        timecard.submit();
    }
}
```

