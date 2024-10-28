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
  ### 3.1 Các lớp phân tích
    Boundary: PaymentForm, ProjectManagementDatabase
    Control: PaymentController
    Entity: Employee
  ### 4.2 Nhiệm vụ của từng lớp
    PaymentForm: Hiển thị giao diện cho việc chọn phương thức thanh toán
    ProjectManagementDatabase: Kết nối và tương tác với cơ sở dữ liệu
    PaymentController: Xử lý logic nghiệp vụ cho việc chọn phương thức thanh toán
    Employee: Lưu trữ thông tin nhân viên
  ### Sequence Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/f5LBJkD04DttAKgimW8BI9XXM20amaYpGA2P4rJiScXeTvlkCbBEDeiv4bUWRCTkCub945bOSdMzrwy-ptdz--ygC7gk2gCmPUVXfYYDMn6fKi8wrILQXdjS5MJvf_F5jlYri-oTCUJVdthtI2dVeiKbrNbpP5nWUC_TNNXZMVDAgUuTZYw7zy85d2JmXummGjd6eI1-S1dabKrPEwk6-H4UvGd9QG9BulN9NLd3mkHGRQRM-B42X6UQm0iQdI5JfrXe59fO4LZ7aBlAPWhaDyvsDA9rcaZ9luahRo578urhU3QbRhHgcfpsIFBU-I6oROzWUg4rG0gQwr0QNBK8QMu8ebIHN1nJlrRFh5V5llfCEMSzi9kzQsUtkx1liR0XfdcCBzjiPDaYjXxrzODpKl11WTeSDD4TScRjI9yh2i8eA6sNW5dcfTaz_YDLCbTnYdHf6xWPLQSfqxwMdr7fWkOzrKsZkWNQ9z0sbpnitBMFl5adRokQxA1_UvXLfbwLjSNMXxVD22OImSEnvRdyxuiYDB81gQU1K-yMzURkuld8_jyJ2FZIwVebTKveJJwFh9zso7c_vg5Aqswi-rZaHm9odcjvQLksonWdnz4NwykYvMLEL_AGluKt0000__y30000)
  ### Class Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/d5JRZjCm47tFLynZLw8Bpn5QxG95gaINbSeFJ9AXXFKbyZWh5SINyS0dyGiuZfFQRhe2dfASCtDcvcJitpz_tR95Otif2dviLOS69TG2cU-iDMtLMzhMMktRRmIlYi8py817ISg-rqR2zm9W3Ts8xCX-qSt7phPQSGaVMhQlzqv67Mvy69EWsb8pnfKmSfwIs0htVjSqXfWJgaBrk5MVTGG2D2rt0e-XrkhAWmUo-wJ42Tyb-YVyJH0FI93T6AFDpWNYWL9ctzUrmq_SZzaLex-wqZjKZXZSU8SMAsGA7ZaRbUDTkoLCrDiPyo4aEw6FH9-m4bI2VyJ-PZZ04ugsGKkRaBYQ5BQpkrSbL5eBGkKp69ye_3y_zfGmT5J29lhA4frNCRjSAOw8d1dhkM6jqKAG2OwSIqoLGiRyTyzsQM7qhD--6zY7U35NZHyoO7ynOpxHVniuMp7nppcm1eMI4Y0vN_zoRkvp9QnhtIjxtykAJ6xxPcvd63tb1gLpDFKtfJcdPTB-nQEPYsGyfgCkdEHSO6PoHruis-4FTNp9NL_VB2nn2JqJ5-U43xzu6poRDkz72RKXjy3ySbnabt1HSRsEyzXgvqzHt99gtBt-1m00__y30000)
## 4. Phân tích ca sử dụng Maintain Timecard
   ### 4.1 Các lớp phân tích
    Boundary: TimecardForm, ProjectManagementDatabase
    Control: TimecardController
    Entity : Timecard, Employee
   ### 4.2 Nhiệm vụ của từng lớp
    TimecardForm: Cung cấp giao diện người dùng để quản lý bảng chấm công
    TimecardController: Điều phối tương tác giữa các lớp boundary và entity
                        Thực hiện logic nghiệp vụ cho các thao tác bảng chấm công
                        Xử lý việc tạo, lấy và nộp bảng chấm công
                        Thực hiện kiểm tra số giờ và ngày tháng
    Employee: Lưu trữ thông tin nhân viên
    Timecard: Lưu trữ dữ liệu bảng chấm công
    ProjectManagementDatabase: Lấy danh sách mã dự án
   ### Sequence Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/d5HBJiCm4Dtx55Ot5AaL-owWwWyMG17q0XDdr1eS6_bJrBEnu4XSWR6ZDAdQH2rPH1ddlVcyDydlzy_OUR0-58g1yCRoUV6fp0wHPIRe7EoEhsI10co-CBQeJr-iUKVXdq336WlKVWOUCd38XD7U6hNdJSjOeMK4axxEMCMzgYYVfuCU1nSRAIF6hYRWfE0BPRxO7ZgyFUXin448TAuwwr-pvkicl6venDVeJp1gH9Ctui8YU5pQU_Ijw5PXKh7f1kmQdqEHeNMKWu7oV3RXi0Mf85F8E5sjEVZmQ6pHpCXG4OZo1Vt_Z6YjiObrg201A_MfB0qjTS0R0LgWkYClStAAB2CP7aoWNjgjmeXAe7vEWWusyN5GJdAURrjGCb9RRTYlJrG8nSUZB6GqBUgTo0S3jXdkO1jB95MbxkQrw5ZgyXOogjyXYKk0CxUs15-mk9LSA-D1NQu2-h9_Zx5Oat9YR1VIXtXYWOwGw5yHygLMkowHkwKTqvr-Nty0003__mC0)
  ### Class Diagram
  ![Diagram](https://www.planttext.com/api/plantuml/png/X5HDJy904BttLsmuwO63Lmu6WnWve0H8F1WFGpk1odxKcLsmCVuo3_ua_uAxfQo5GcpIf7spC_FUcsb_lhxxR86iKp99KWdCOfuhJ86oEqDAV2IYkhAS2mdbFdPnUOWFLa1BV71gWSGno2kp7H8P6YCpBF4uQugGFMhPhhf4UsySyKWNpZRH6KfCBMR7_JwFoG-CjcIaH8eIKaAmsEf5Q2d7JJl0S0fq2vNR5hm1cMU-UiKwekaAq_KiP33dHiyiMDU8WaoT39IC1TdCxCPwj_wUWgwiYng7gf2cHAoLTGNMm2Yh0GqAwqS5xrNf2T8JuleeOruM-EVkm16XRglpeJ6ytqXfjh2GKMJBz4Z8ra0aLErO4BFlhxF6syvKFzOcLfaLZuSPSIzs6dgWV7wf-K6s0o9XLmJp3Z4lecMq43dFzisRYYPaNlsYZK7xjLM-lMS62s2CsnJiEhdq-z4rexlI1nzMjtjzQbbxmZ5oSY8I4kBaUtwkWThPat4a_vuyBxKdtXm6tvFOjtFLyKcYuskMdMQJ5N2IzFrO_O_a5m00__y30000)
## 5. Hợp nhất kết quả phân tích

