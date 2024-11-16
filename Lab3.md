# 1. Subsystem context diagrams
## a. Hệ thống con BankSystem:
![](https://www.planttext.com/api/plantuml/png/d591Ri8m4BplArQvb4e5xWWXLBXmG-85MxE05SUEl9kAgE9bFVH9_KBZH8GqlVNajNTcF3lsz-VNMfIYLeK3aDpwaY8LQ49H1izU3rexniX6oPyT0wZLvk2LV7weHRd0G_KcNRK9NlcgkBLqRaG0dd3B9-lv8ITW78dWdkeOd4kCj7B4vT9qczKAFm1nFiTOUImxuEGPRW2sqOydCeoxWO64nYENGQnEg54s5pRv0k_L2pQya0YBrlVEdq8iI6tmhMfZoshTm-_x4HIW99FJcJ5xJBoFuLfdI88ZFzsKOvF_jubuIrRxG2ExjYCNMmhyJNCwNVtAQ87PqQPNl3iGR2yLVBUKmH2Qg7qMuyOub65_EPiD9WPOip-cR_K3003__mC0)

### Các thành phần chính

- PayrollController: Thành phần điều khiển của hệ thống chính, gửi lệnh thực hiện giao dịch chuyển tiền.
- IBankSystem Interface: Cung cấp giao diện chuẩn để thực hiện các giao dịch ngân hàng, đảm bảo tính nhất quán trong việc gọi hàm từ các hệ thống khác.
- Paycheck: Đại diện cho phiếu lương, chứa thông tin chi tiết về số tiền cần chuyển.
- BankInformation: Đại diện cho thông tin ngân hàng, bao gồm chi tiết tài khoản ngân hàng nơi tiền sẽ được gửi.
- BankSystem (Subsystem Proxy): Triển khai các phương thức được định nghĩa trong giao diện IBankSystem để thực hiện giao dịch thực tế.

  
### Interface của hệ thống con BankSystem

Interface IBankSystem cung cấp phương thức sau:

deposit(aPaycheck: Paycheck, intoBank: BankInformation):

Đầu vào:

aPaycheck: Đối tượng phiếu lương chứa thông tin về số tiền cần chuyển.

intoBank: Đối tượng thông tin ngân hàng chứa thông tin tài khoản đích.

Chức năng:

Thực hiện việc chuyển tiền từ phiếu lương (Paycheck) tới tài khoản ngân hàng được chỉ định (BankInformation).
  
## b. Hệ thống con PrintService:

![](https://www.planttext.com/api/plantuml/png/Z5AzRi8m4DxlAKvP2WEmeoX2AWjR99xWwXx1YcEdzWKHLJnPXpvINw5sKq83IoUVVVVzdVpryRa9GbwwnW24MjkMF3MeNDCworRsqXj6pqh8LeO1H4jyABsEFVOdhHZttKleWt23pyuAdmMtcgf80_24MpveopV20CfG25XIxvqn2P5EzfZdQhWK1Ru3ucg5lhFO_f6QpU424E_i3nILTnCV2JICHt9rP5NFw5gjyLhDqvGYgzZye0VEw4nBFmu1jAHggXYpMxhIktEV8GLyaFtDzE3cltxk7I5UagjnVPuDYNOs77KRu75tYqLnjumrPe7jww0VyMyT1y6JfWocWmawnfwsykLoaWbW4odJL_a6003__mC0)

### Các thành phần chính của hệ thống con

- PayrollController:
Là thành phần điều khiển từ hệ thống chính, gửi lệnh đến PrintService để yêu cầu in các phiếu lương.

- IPrintService Interface:
Định nghĩa giao diện chuẩn cho các dịch vụ in ấn, đảm bảo các thành phần khác có thể gọi tới các chức năng in ấn mà không cần biết chi tiết triển khai.

- Paycheck:
Là dữ liệu đầu vào chứa thông tin cần in, như thông tin nhân viên, số tiền lương, và các chi tiết khác.

- PrintService Subsystem Proxy:
Thực hiện việc triển khai cụ thể của các phương thức được định nghĩa trong giao diện IPrintService.
Kết nối và tương tác với các thiết bị in.

### Mô tả giao diện IPrintService
Phương thức:

printPaycheck(aPaycheck: Paycheck): Thực hiện in phiếu lương dựa trên đối tượng phiếu lương được cung cấp.

cancelPrint(): Hủy bỏ yêu cầu in trong trường hợp có lỗi hoặc thay đổi yêu cầu.

## c. Hệ thống con ProjectManagementDatabase:

![](https://www.planttext.com/api/plantuml/png/d5FBQW914BptLpHxYKBKkuW8cX0F2O9VqAxjEd4UcvdUu1ByiXpoIVc5xEYkago1aDCmFTLLNTNCv_l790XvAOm623jbS_9aC7KcTvQjBANKZ9vJ8Pjf1X0bLM7XtNDLUoHB6PiADoEX5GN6PR4APH0sE7LMU2yuKvHLd00tEEEDidnX3v1g2W4NL7gdTUo89tiSZTBJPJp6Dq0S3D0SnJ0_IUFM5Jx00K1LCdv3AUEy7kiyJEp4Z6Mw9P_nKs5Mx4EdMrSRD0if7JeryNmsnALuPRCZhiZN95n37w9cXqskNSbyGTwUfXdYlNOatJXLvKv9sGJLNE_grYCHG4xfBdfABgbL3VioGGfupKmTrpMRlndzkzL_caKyHCFdxNhM9ChPi5LvWFPgUxrnUrD3J0BRzNcxBmLxnG5V5INGGaUA9jchZzzpRa56_VxF404cbNxy1by0003__mC0)

### Các thành phần chính của hệ thống con

- PayrollController:
Gửi các yêu cầu đến hệ thống con để truy xuất hoặc xác nhận thông tin mã dự án và giờ làm việc liên quan.

- IProjectDatabase Interface:
Cung cấp giao diện chuẩn để truy xuất và cập nhật thông tin từ hệ thống cơ sở dữ liệu dự án.

- Project:
Đại diện cho một dự án với các thuộc tính như mã dự án, tên dự án, và trạng thái.

- EmployeeHours:
Lưu trữ thông tin giờ làm việc của nhân viên, được liên kết với các dự án cụ thể.

- ProjectDatabase Subsystem Proxy:
Triển khai các phương thức được định nghĩa trong giao diện IProjectDatabase để thao tác với cơ sở dữ liệu dự án.

### Mô tả giao diện IProjectDatabase

Phương thức:

getChargeNumbers(): Trả về danh sách mã công việc có sẵn.

getProjectDetails(projectID: String): Trả về thông tin chi tiết của một dự án.

updateProjectHours(employeeID: String, hours: Float): Cập nhật giờ làm việc của nhân viên vào dự án tương ứng.


# 2. Analysis class to design element map
|  Analysis Class | Design Element |  
|-----------------|----------------|
| LoginForm | LoginForm|
| MaintainTimecardForm | MainEmployeeForm |
| TimecardController | TimecardController |
| PayrollController | PayrollController |
| PayCheck | PayCheck |
| BankService | BankService |
| SystemClockInterface | SystemCLockInterface |
| PayrollController | PayrollControllerImpl |
| Employee | EmployeeEntity |
| Timecard | TimecardEntity |
| Payroll | PayrollProcessor |
| BankTransaction | BankTransactionProcessor |
| PaymentUI | PaymentUIComponent |
| PrintService | PrintServiceProcessor |

# 3. Design element to owning package map
|  Design Element | "Owning" Package |  
|-----------------|----------------|
| LoginForm | Middleware::Security::GUIFramwork |
| MainEmployeeForm | Applications::Employee Activities |
| TimecardController | Applications::Employee Activities |
| SystemClockInterface | Applications::Payroll |
| PayrollController | Applications: Payroll |
| PayCheck | Business Services::Payroll Artifacts |
| BankService | Business::Banking |
| EmployeeEntity | Data Access::Employee Management |
| TimecardEntity | Data Access::Employee Management |
| PayrollProcessor | Business Services::Payroll Processing |
| BankTransactionProcessor | Business Services::Banking |
| PaymentUIComponent | Middleware::User Interface Components |
| PaymentUIComponent | Middleware::Print Services |


# 4. Architectural layers and their dependencies
  ![Diagram](https://www.planttext.com/api/plantuml/png/b591QiCm4Bph5IBtVA04azJqba8W-S0YBOwmh1MId69ANfP3dzGlL0uEbgocK1rtPdPs1dtVlhO-W0jzfva5qKA3VBMpLYi1GP7XUnZGhVWdu_493Txpjyvg6X2Fw2vAO8ASL8S2dAp914TQeql00mpZBC6kRFPyxRqo66dJrjmoQkipYlQvPObCVWT78kwbt6wpULTIQlm0XrMLc-sfQPHfoesxFfpHXAcQ4ZyEFc1NQnBjQBReYQ_NrJ88V-6zHy_AukxiHRW7ksZoiJhB-pSx3ncvcXhFoQAxXvjFIgylHAd1RFnFwg-rHWNCysVIfF4ei8ukIgBd8TxEs1QD7F_r3m000F__0m00)
