# Phân tích ca sử dụng Create Employee
  ## Các lớp phân tích

  ## Nhiệm vụ của từng lớp

  ## Sequence Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/d5HBJiCm4Dtx55Ot5AaL-owWwWyMG17q0XDdr1eS6_bJrBEnu4XSWR6ZDAdQH2rPH1ddlVcyDydlzy_OUR0-58g1yCRoUV6fp0wHPIRe7EoEhsI10co-CBQeJr-iUKVXdq336WlKVWOUCd38XD7U6hNdJSjOeMK4axxEMCMzgYYVfuCU1nSRAIF6hYRWfE0BPRxO7ZgyFUXin448TAuwwr-pvkicl6venDVeJp1gH9Ctui8YU5pQU_Ijw5PXKh7f1kmQdqEHeNMKWu7oV3RXi0Mf85F8E5sjEVZmQ6pHpCXG4OZo1Vt_Z6YjiObrg201A_MfB0qjTS0R0LgWkYClStAAB2CP7aoWNjgjmeXAe7vEWWusyN5GJdAURrjGCb9RRTYlJrG8nSUZB6GqBUgTo0S3jXdkO1jB95MbxkQrw5ZgyXOogjyXYKk0CxUs15-mk9LSA-D1NQu2-h9_Zx5Oat9YR1VIXtXYWOwGw5yHygLMkowHkwKTqvr-Nty0003__mC0)
  ## Class Diagram


# Phân tích ca sử dụng Maintain Purchase Order
  ## Các lớp phân tích

  ## Nhiệm vụ của từng lớp

  ## Sequence Diagram
  
  ## Class Diagram


# Phân tích ca sử dụng Login
  ## Các lớp phân tích

  ## Nhiệm vụ của từng lớp

  ## Sequence Diagram
  
  ## Class Diagram



# Phân tích ca sử dụng Create Adminstrative Report
  ## Các lớp phân tích

  ## Nhiệm vụ của từng lớp

  ## Sequence Diagram
  
  ## Class Diagram



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

