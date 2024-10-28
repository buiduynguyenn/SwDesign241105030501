# PHÂN TÍCH KIẾN TRÚC, CƠ CHẾ, CA SỬ DỤNG
## 1. Phân tích kiến trúc
* Đề xuất kiến trúc
  - Kiến trúc ba lớp (Three-Layer Architecture) là một mô hình phổ biến trong phát triển phần mềm, giúp tách biệt các thành phần của hệ thống thành ba lớp chính: Lớp Giao diện Người dùng (Presentation Layer), Lớp Xử lý Nghiệp vụ (Business Logic Layer), và Lớp Truy cập Dữ liệu (Data Access Layer)
* Giải thích lý do lựa chọn
  - Tính phân tách rõ ràng: Kiến trúc phân lớp giúp tách biệt các thành phần chức năng của hệ thống thành các lớp độc lập, tăng tính mềm dẻo và dễ bảo trì.
  - Quản lý dữ liệu và tích hợp: Lớp Hạ tầng cho phép tách biệt logic truy xuất và thao tác dữ liệu, dễ dàng tích hợp với các nguồn dữ liệu khác như DB2 và Project Management Database.
  - Tái sử dụng: Các lớp trong kiến trúc phân lớp có thể được tái sử dụng trong các dự án khác, giúp tiết kiệm thời gian và chi phí phát triển.
  - Bảo mật và kiểm soát truy cập: Kiến trúc phân lớp cho phép tập trung logic kiểm soát truy cập vào một lớp riêng, dễ dàng quản lý và bảo trì.
* Ý nghĩa từng thành phần trong kiến trúc
  - Lớp Giao diện Người dùng (Presentation Layer):
Lớp này giúp người dùng tương tác với hệ thống một cách dễ dàng và trực quan. Nó không chứa logic nghiệp vụ, giúp tách biệt giao diện người dùng khỏi các phần khác của hệ thống, từ đó dễ dàng thay đổi giao diện mà không ảnh hưởng đến logic nghiệp vụ.
  - Lớp Xử lý Nghiệp vụ (Business Logic Layer):
Lớp này là nơi thực hiện các quy tắc và logic của hệ thống, đảm bảo rằng các tính toán và quy trình được thực hiện chính xác. Nó đóng vai trò trung gian giữa lớp Giao diện Người dùng và lớp Truy cập Dữ liệu, giúp tổ chức mã nguồn một cách rõ ràng và dễ bảo trì.
  - Lớp Truy cập Dữ liệu (Data Access Layer):
Lớp này giúp tách biệt logic truy cập dữ liệu khỏi các phần khác của hệ thống, cho phép dễ dàng thay đổi cơ sở dữ liệu mà không ảnh hưởng đến các lớp khác. Nó cũng đảm bảo rằng các truy vấn và thao tác dữ liệu được thực hiện một cách hiệu quả và an toàn.
* Biểu đồ package mô tả kiến trúc

  ![Diagram](https://www.planttext.com/api/plantuml/png/R951JiCm44NtESMe6rQz0YeDMI0LgRImGbrCpITOjSUHnn54Y9Enu4XS0QU9H5l5op_Zz__C_7x_B3HnJArtHSFcm3LejevGIE9aWz2AEyGPVHQKt_EJ8jAT9CHNDjWDugFre4fIx4PXWoR4fBlYg_YdBbkr0bLQXTgQ2-wM7SUEIdQcTKVZ4LNvneKEe7kMZF4vrrWfW_TMjS-uZi5aifNwtFAM4zEDCKVNCx--icS5bK44viJmeKKEKdt0j8EQWLUqmP1AtsoZj4Tw1uHSpzJYSYiqdrzFZtIwgg5hShwflqFxPEu5vAK_u1y0003__mC0)

## 2. Cơ chế phân tích
* Persistency : Hệ thống cần lưu trữ thông tin về nhân viên, thời gian làm việc, và các thông tin thanh toán một cách bền vững. Điều này đảm bảo rằng dữ liệu không bị mất khi hệ thống tắt hoặc gặp sự cố.
* Security : Bảo mật là rất quan trọng trong hệ thống payroll, vì nó liên quan đến thông tin nhạy cảm của nhân viên và dữ liệu tài chính.
* Legacy Interface : Hệ thống mới cần tương tác với cơ sở dữ liệu kế thừa (Project Management Database) mà không làm gián đoạn hoạt động của nó.
## 3. Phân tích ca sử dụng Payment
* Lớp Boundary:
  - PaymentMethodUI: Lớp giao diện người dùng để hiển thị và nhận đầu vào từ nhân viên về phương thức thanh toán.
  Nhiệm vụ: Hiển thị giao diện để nhân viên chọn phương thức thanh toán, nhận đầu vào từ nhân viên và gửi yêu cầu tới lớp điều khiển.
* Lớp Control:
  - PaymentMethodController: Lớp điều khiển xử lý logic nghiệp vụ cho việc chọn phương thức thanh toán.
  Nhiệm vụ: Kiểm tra thông tin nhân viên, yêu cầu thông tin bổ sung (nếu cần), cập nhật phương thức thanh toán cho nhân viên, tương tác với các lớp thực thể.
  Thuộc tính: employeeRepository (truy cập thông tin nhân viên), paymentMethodRepository (truy cập thông tin phương thức thanh toán).
* Lớp Entity:
  - Employee: Lớp thực thể đại diện cho thông tin nhân viên.
  Thuộc tính: employeeId, name, address, paymentMethod, ...
  Quan hệ: 1 Employee có 1 PaymentMethod.
  - PaymentMethod: Lớp thực thể đại diện cho các phương thức thanh toán khả dụng.
  Thuộc tính: paymentMethodId, paymentMethodType (nhận trực tiếp, gửi bưu điện, chuyển khoản ngân hàng), bankName, accountNumber, ...
  Quan hệ: 1 PaymentMethod được sử dụng bởi nhiều Employee.
* Mối quan hệ giữa các lớp:
  - PaymentMethodUI sẽ tương tác với PaymentMethodController để xử lý yêu cầu chọn phương thức thanh toán từ người dùng.
  - PaymentMethodController sẽ tương tác với Employee và PaymentMethod để lấy thông tin cần thiết và cập nhật phương thức thanh toán cho nhân viên.
  - Employee có quan hệ 1-1 với PaymentMethod, nghĩa là mỗi nhân viên có một phương thức thanh toán.
  - PaymentMethod có quan hệ 1-nhiều với Employee, nghĩa là một phương thức thanh toán có thể được sử dụng bởi nhiều nhân viên.
## 4. Phân tích ca sử dụng Maintain Timecard
## 5. Hợp nhất kết quả phân tích

