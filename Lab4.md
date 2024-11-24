# 1.Create Administrative Report 
## Brief Description 
  Trường hợp sử dụng này cho phép Quản trị viên tiền lương tạo báo cáo "Tổng số giờ làm việc" hoặc "Tổng lương năm đến nay".
## Flow of Events 
### Basic Flow 
1. Trường hợp sử dụng bắt đầu khi Quản trị viên tiền lương yêu cầu hệ thống tạo báo cáo quản trị.

- Hệ thống yêu cầu Quản trị viên tiền lương chỉ định các tiêu chí báo cáo sau:
- Loại báo cáo (tổng số giờ làm việc hoặc tổng lương năm đến nay)
- Ngày bắt đầu và kết thúc của báo cáo
- Tên nhân viên (các nhân viên)

  
2. Sau khi Quản trị viên tiền lương cung cấp thông tin yêu cầu, hệ thống cung cấp cho Quản trị viên tiền lương một báo cáo đáp ứng các tiêu chí báo cáo.

3. Quản trị viên tiền lương có thể yêu cầu hệ thống lưu báo cáo. Tại thời điểm đó, hệ thống yêu cầu Quản trị viên tiền lương cung cấp tên và vị trí để lưu báo cáo.

4. Sau khi Quản trị viên tiền lương cung cấp thông tin yêu cầu và xác nhận quyết định lưu báo cáo, hệ thống lưu báo cáo vào tên và vị trí đã chỉ định.

5. Nếu Quản trị viên tiền lương không chọn lưu báo cáo, báo cáo sẽ bị loại bỏ.
### Alternative Flows 
#### Thông tin yêu cầu không khả dụng:
Nếu trong Dòng chính, thông tin yêu cầu không khả dụng, hệ thống sẽ hiển thị thông báo lỗi.
Quản trị viên tiền lương có thể chọn quay lại đầu Dòng chính hoặc hủy thao tác, tại thời điểm đó trường hợp sử dụng kết thúc.

#### Định dạng không hợp lệ hoặc thông tin không đủ:
Nếu trong Dòng chính, Quản trị viên tiền lương chưa chỉ định đủ thông tin để tạo báo cáo đã chọn, hệ thống sẽ nhắc người dùng nhập thông tin còn thiếu. Quản trị viên tiền lương có thể nhập thông tin còn thiếu hoặc chọn hủy thao tác, tại thời điểm đó trường hợp sử dụng kết thúc.
## Special Requirements 
Không có.
## Pre-Conditions 
Quản trị viên tiền lương phải đăng nhập vào hệ thống để trường hợp sử dụng này bắt đầu.
## Post-Conditions 
Trạng thái hệ thống không thay đổi bởi trường hợp sử dụng này.
## Extension Points 
Không có.

# 2. Create Employee Report 
## Brief Description 
Trường hợp sử dụng này cho phép Nhân viên tạo báo cáo "Tổng số giờ làm việc", "Tổng số giờ làm việc cho dự án", "Nghỉ phép/ốm đau" hoặc "Tổng lương năm đến nay".
## Flow of Events 
### Basic Flow 
Trường hợp sử dụng này bắt đầu khi Nhân viên muốn tạo báo cáo "Tổng số giờ làm việc", "Tổng số giờ làm việc cho dự án", "Nghỉ phép/ốm đau" hoặc "Tổng lương năm đến nay".

1. Hệ thống yêu cầu Nhân viên chỉ định các tiêu chí báo cáo sau:
- Loại báo cáo (Tổng số giờ làm việc, Tổng số giờ làm việc cho dự án, Nghỉ phép/ốm đau hoặc Tổng lương năm đến nay)
- Ngày bắt đầu và kết thúc của báo cáo
2. Nếu Nhân viên chọn báo cáo "Tổng số giờ làm việc cho dự án", hệ thống sẽ truy xuất và hiển thị danh sách các mã dự án có sẵn từ Cơ sở dữ liệu Quản lý Dự án. Sau đó, hệ thống yêu cầu Nhân viên chọn một mã dự án.
  
3. Sau khi Nhân viên cung cấp thông tin yêu cầu, hệ thống cung cấp cho Nhân viên một báo cáo đáp ứng các tiêu chí báo cáo.

4. Nhân viên có thể yêu cầu hệ thống lưu báo cáo. Tại thời điểm đó, hệ thống yêu cầu Nhân viên cung cấp tên và vị trí để lưu báo cáo.

5. Sau khi Nhân viên cung cấp thông tin yêu cầu và xác nhận quyết định lưu báo cáo, hệ thống lưu báo cáo vào tên và vị trí đã chỉ định.

6. Nếu Nhân viên không chọn lưu báo cáo, báo cáo sẽ bị loại bỏ.
### Alternative Flows 
#### Thông tin yêu cầu không khả dụng:
Nếu trong Dòng chính, thông tin yêu cầu không khả dụng, hệ thống sẽ hiển thị thông báo lỗi.
Nhân viên có thể chọn quay lại đầu Dòng chính hoặc hủy thao tác, tại thời điểm đó trường hợp sử dụng kết thúc.

#### Định dạng không hợp lệ hoặc thông tin không đủ:
Nếu trong Dòng chính, Nhân viên chưa chỉ định đủ thông tin để tạo báo cáo đã chọn, hệ thống sẽ nhắc người dùng nhập thông tin còn thiếu. Nhân viên có thể nhập thông tin còn thiếu hoặc chọn hủy thao tác, tại thời điểm đó trường hợp sử dụng kết thúc.
## Special Requirements  
Không có.
## Pre-Conditions 
Nhân viên phải đăng nhập vào hệ thống trước khi trường hợp sử dụng này bắt đầu.
## Post-Conditions 
Trạng thái hệ thống không thay đổi bởi trường hợp sử dụng này.
## Extension Points 
Không có.

# 3.Login
## Brief Description 
Trường hợp sử dụng này mô tả cách người dùng đăng nhập vào Hệ thống tiền lương.
## Flow of Events 
### Basic Flow 
Trường hợp sử dụng này bắt đầu khi người dùng muốn đăng nhập vào Hệ thống tiền lương.

1. Người dùng nhập tên và mật khẩu của mình.
   
2. Hệ thống xác thực tên và mật khẩu đã nhập và đăng nhập người dùng vào hệ thống.
### Alternative Flows 
#### Tên/Mật khẩu không hợp lệ
Nếu trong Dòng chính, người dùng nhập tên và/hoặc mật khẩu không hợp lệ, hệ thống sẽ hiển thị thông báo lỗi. Người dùng có thể chọn quay lại đầu Dòng chính hoặc hủy đăng nhập, tại thời điểm đó trường hợp sử dụng kết thúc.
## Special Requirements  
Không có.
## Pre-Conditions 
Hệ thống ở trạng thái đăng nhập và màn hình đăng nhập được hiển thị.
## Post-Conditions 
Nếu trường hợp sử dụng thành công, người dùng hiện đã đăng nhập vào hệ thống. Nếu không, trạng thái hệ thống không thay đổi.
## Extension Points 
Không có.

# 4.Maintain Employee Information 
## Brief Description
Trường hợp sử dụng này cho phép Quản trị viên tiền lương duy trì thông tin nhân viên. Bao gồm thêm, sửa đổi và xóa thông tin nhân viên khỏi hệ thống.
## Flow of Events 
### Basic Flow 
Trường hợp sử dụng này bắt đầu khi Quản trị viên tiền lương muốn thêm, sửa đổi và/hoặc xóa thông tin nhân viên khỏi hệ thống.

1. Hệ thống yêu cầu Quản trị viên tiền lương chỉ định chức năng mà họ muốn thực hiện (Thêm nhân viên, Cập nhật nhân viên hoặc Xóa nhân viên)
   
2. Sau khi Quản trị viên tiền lương cung cấp thông tin yêu cầu, một trong các dòng phụ được thực thi.
- Nếu Quản trị viên tiền lương chọn "Thêm nhân viên", dòng phụ Thêm nhân viên được thực thi.
- Nếu Quản trị viên tiền lương chọn "Cập nhật nhân viên", dòng phụ Cập nhật nhân viên được thực thi.
- Nếu Quản trị viên tiền lương chọn "Xóa nhân viên", dòng phụ Xóa nhân viên được thực thi.
#### Thêm nhân viên

1. Hệ thống yêu cầu Quản trị viên tiền lương nhập thông tin nhân viên. Bao gồm:
- Tên
- Loại nhân viên (giờ công, lương cố định, hoa hồng)
- Địa chỉ gửi thư
- Số an sinh xã hội
- Khấu trừ thuế tiêu chuẩn
- Khấu trừ khác (401k, y tế)
- Số điện thoại
- Tỷ lệ giờ công (đối với nhân viên giờ công)
- Lương (đối với nhân viên lương cố định và hoa hồng)
- Tỷ lệ hoa hồng (đối với nhân viên hoa hồng)
- Giới hạn giờ làm (một số nhân viên có thể không làm thêm giờ)
2. Sau khi Quản trị viên tiền lương cung cấp thông tin yêu cầu, hệ thống sẽ tạo và gán một số định danh nhân viên duy nhất cho nhân viên và đặt phương thức nhận lương mặc định là "nhận trực tiếp". Nhân viên được thêm vào hệ thống.
3. Hệ thống cung cấp cho Quản trị viên tiền lương ID nhân viên mới.
#### Cập nhật nhân viên

1. Hệ thống yêu cầu Quản trị viên tiền lương nhập ID nhân viên.
2. Quản trị viên tiền lương nhập ID nhân viên. Hệ thống truy xuất và hiển thị thông tin nhân viên.
3. Quản trị viên tiền lương thực hiện các thay đổi mong muốn đối với thông tin nhân viên. Bao gồm bất kỳ thông tin nào được chỉ định trong dòng phụ Thêm nhân viên.
4. Sau khi Quản trị viên tiền lương cập nhật thông tin cần thiết, hệ thống cập nhật hồ sơ nhân viên bằng thông tin đã cập nhật.
#### Xóa nhân viên

1. Hệ thống yêu cầu Quản trị viên tiền lương chỉ định ID nhân viên.
2. Quản trị viên tiền lương nhập ID nhân viên. Hệ thống truy xuất và hiển thị thông tin nhân viên.
3. Hệ thống nhắc Quản trị viên tiền lương xác nhận việc xóa nhân viên.
4. Quản trị viên tiền lương xác minh việc xóa.
5. Hệ thống đánh dấu hồ sơ nhân viên để xóa. Lần chạy lương tiếp theo, hệ thống sẽ tạo phiếu lương cuối cùng cho nhân viên đã xóa và xóa nhân viên khỏi hệ thống.
### Alternative Flows 
#### Nhân viên không tìm thấy
Nếu trong dòng phụ Cập nhật nhân viên hoặc Xóa nhân viên, nhân viên với số ID đã chỉ định không tồn tại, hệ thống sẽ hiển thị thông báo lỗi. Quản trị viên tiền lương có thể nhập một số ID khác hoặc hủy thao tác, tại thời điểm đó trường hợp sử dụng kết thúc.

#### Hủy xóa
Nếu trong dòng phụ Xóa nhân viên, Quản trị viên tiền lương quyết định không xóa nhân viên, việc xóa sẽ bị hủy và Dòng chính được khởi động lại từ đầu.
## Special Requirements
Không có.
## Pre-Conditions 
Quản trị viên tiền lương phải đăng nhập vào hệ thống trước khi trường hợp sử dụng này bắt đầu.
## Post-Conditions 
Nếu trường hợp sử dụng thành công, thông tin nhân viên được thêm, cập nhật hoặc xóa khỏi hệ thống. Nếu không, trạng thái hệ thống không thay đổi.
## Extension Points 
Không có.

# 5.Maintain Purchase Order 
## Brief Description 
Trường hợp sử dụng này cho phép Nhân viên kinh doanh ghi nhận và duy trì các đơn đặt hàng. Bao gồm thêm, sửa đổi và xóa đơn đặt hàng. Nhân viên kinh doanh phải ghi nhận từng đơn đặt hàng của họ để nhận hoa hồng.
## Flow of Events 
### Basic Flow 
Trường hợp sử dụng này bắt đầu khi Nhân viên kinh doanh muốn thêm, sửa đổi và/hoặc xóa thông tin đơn đặt hàng khỏi hệ thống.

1. Hệ thống yêu cầu Nhân viên kinh doanh chỉ định chức năng mà họ muốn thực hiện (Tạo đơn đặt hàng, Cập nhật đơn đặt hàng hoặc Xóa đơn đặt hàng)
2. Sau khi Nhân viên kinh doanh cung cấp thông tin yêu cầu, một trong các dòng phụ được thực thi.
- Nếu Nhân viên kinh doanh chọn "Tạo đơn đặt hàng", dòng phụ Tạo đơn đặt hàng được thực thi.
- Nếu Nhân viên kinh doanh chọn "Cập nhật đơn đặt hàng", dòng phụ Cập nhật đơn đặt hàng được thực thi.
- Nếu Nhân viên kinh doanh chọn "Xóa đơn đặt hàng", dòng phụ Xóa đơn đặt hàng được thực thi.
#### Tạo đơn đặt hàng

1. Hệ thống yêu cầu Nhân viên kinh doanh nhập thông tin đơn đặt hàng. Bao gồm:
- Người liên hệ khách hàng
- Địa chỉ thanh toán của khách hàng
- Sản phẩm (các sản phẩm) đã mua
- Ngày
2. Sau khi Nhân viên kinh doanh cung cấp thông tin yêu cầu, hệ thống sẽ tạo và gán một số đơn đặt hàng duy nhất cho đơn đặt hàng. Đơn đặt hàng được thêm vào hệ thống cho Nhân viên kinh doanh.
3. Hệ thống cung cấp cho Nhân viên kinh doanh ID đơn đặt hàng mới.
#### Cập nhật đơn đặt hàng

1. Hệ thống yêu cầu Nhân viên kinh doanh nhập ID đơn đặt hàng.
2. Nhân viên kinh doanh nhập ID đơn đặt hàng.
3. Hệ thống truy xuất đơn đặt hàng liên kết với ID đơn đặt hàng.
4. Hệ thống xác minh rằng đơn đặt hàng là đơn đặt hàng cho Nhân viên kinh doanh và đơn đặt hàng đang mở.
5. Hệ thống hiển thị đơn đặt hàng.
6. Nhân viên kinh doanh thực hiện các thay đổi mong muốn đối với thông tin đơn đặt hàng. Bao gồm bất kỳ thông tin nào được chỉ định trong dòng phụ Tạo đơn đặt hàng.
7. Sau khi Nhân viên kinh doanh cập nhật thông tin cần thiết, hệ thống cập nhật đơn đặt hàng bằng thông tin đã cập nhật.
#### Xóa đơn đặt hàng

1. Hệ thống yêu cầu Nhân viên kinh doanh chỉ định ID đơn đặt hàng.
2. Nhân viên kinh doanh nhập ID đơn đặt hàng.
3. Hệ thống truy xuất đơn đặt hàng liên kết với ID đơn đặt hàng.
4. Hệ thống xác minh rằng đơn đặt hàng là đơn đặt hàng cho Nhân viên kinh doanh và đơn đặt hàng đang mở.
5. Hệ thống hiển thị đơn đặt hàng.
6. Hệ thống nhắc Nhân viên kinh doanh xác nhận việc xóa đơn đặt hàng.
7. Nhân viên kinh doanh xác minh việc xóa.
8. Hệ thống xóa đơn đặt hàng khỏi hệ thống.
### Alternative Flows 
#### Đơn đặt hàng không tìm thấy
Nếu trong dòng phụ Cập nhật đơn đặt hàng hoặc Xóa đơn đặt hàng, đơn đặt hàng với số ID đã chỉ định không tồn tại, hệ thống sẽ hiển thị thông báo lỗi. Nhân viên kinh doanh có thể nhập một số ID khác hoặc hủy thao tác, tại thời điểm đó trường hợp sử dụng kết thúc.

#### Truy cập đơn đặt hàng không hợp lệ
Nếu trong dòng phụ Cập nhật đơn đặt hàng hoặc Xóa đơn đặt hàng, Nhân viên kinh doanh cố gắng truy cập đơn đặt hàng không phải của mình, hệ thống sẽ hiển thị thông báo lỗi. Nhân viên kinh doanh có thể nhập một số ID khác hoặc hủy thao tác, tại thời điểm đó trường hợp sử dụng kết thúc.

#### Đơn đặt hàng đã đóng
Nếu trong dòng phụ Cập nhật đơn đặt hàng hoặc Xóa đơn đặt hàng, Nhân viên kinh doanh cố gắng truy cập đơn đặt hàng đã đóng, hệ thống sẽ hiển thị thông báo lỗi. Nhân viên kinh doanh có thể nhập một số ID khác hoặc hủy thao tác, tại thời điểm đó trường hợp sử dụng kết thúc.

#### Hủy xóa
Nếu trong dòng phụ Xóa đơn đặt hàng, Nhân viên kinh doanh quyết định không xóa đơn đặt hàng, việc xóa sẽ bị hủy và Dòng chính được khởi động lại từ đầu.
## Special Requirements  
Không có.
## Pre-Conditions 
Nhân viên kinh doanh phải đăng nhập vào hệ thống trước khi trường hợp sử dụng này bắt đầu.
## Post-Conditions 
Nếu trường hợp sử dụng thành công, thông tin đơn đặt hàng được thêm, cập nhật hoặc xóa khỏi hệ thống. Nếu không, trạng thái hệ thống không thay đổi.
## Extension Points 
Không có.


# 6.Maintain Timecard 
## Brief Description 
Trường hợp sử dụng này cho phép Nhân viên cập nhật và nộp thông tin thẻ công. Nhân viên giờ công và lương cố định phải nộp thẻ công hàng tuần, ghi lại tất cả giờ làm việc trong tuần đó và dự án mà giờ làm được tính phí. Nhân viên chỉ có thể thay đổi thẻ công cho kỳ lương hiện tại và trước khi thẻ công được nộp.
## Flow of Events 
### Basic Flow 
Trường hợp sử dụng này bắt đầu khi Nhân viên muốn nhập giờ làm việc vào thẻ công hiện tại của mình.

1. Hệ thống truy xuất và hiển thị thẻ công hiện tại cho Nhân viên. Nếu không có thẻ công cho Nhân viên cho kỳ lương hiện tại, hệ thống sẽ tạo một thẻ công mới. Ngày bắt đầu và kết thúc của thẻ công được hệ thống đặt và Nhân viên không thể thay đổi.
2. Hệ thống truy xuất và hiển thị danh sách các mã dự án có sẵn từ Cơ sở dữ liệu Quản lý Dự án.
3. Nhân viên chọn các mã dự án phù hợp và nhập số giờ làm việc cho bất kỳ ngày nào (trong phạm vi ngày của thẻ công).
4. Sau khi Nhân viên nhập thông tin, hệ thống lưu thẻ công.
#### Nộp thẻ công

1. Bất cứ lúc nào, Nhân viên có thể yêu cầu hệ thống nộp thẻ công.
2. Tại thời điểm đó, hệ thống gán ngày hiện tại cho thẻ công làm ngày nộp và thay đổi trạng thái của thẻ công thành "đã nộp". Không có thay đổi nào được phép đối với thẻ công sau khi nó đã được nộp.
3. Hệ thống xác thực thẻ công bằng cách kiểm tra số giờ làm việc so với mỗi mã dự án. Tổng số giờ làm việc đối với tất cả các mã dự án không được vượt quá bất kỳ giới hạn nào được thiết lập cho Nhân viên (ví dụ: Nhân viên có thể không được phép làm thêm giờ).
4. Hệ thống giữ lại số giờ làm việc cho mỗi mã dự án trong thẻ công.
5. Hệ thống lưu thẻ công.
6. Hệ thống khóa thẻ công và không cho phép thay đổi thêm sau khi thẻ công được nộp.
### Alternative Flows 
#### Số giờ không hợp lệ
Nếu trong Dòng chính, số giờ không hợp lệ được nhập cho một ngày duy nhất (>24) hoặc số được nhập vượt quá số giờ tối đa cho phép đối với Nhân viên, hệ thống sẽ hiển thị thông báo lỗi và nhắc nhập số giờ hợp lệ. Nhân viên phải nhập số hợp lệ hoặc hủy thao tác, trong trường hợp đó trường hợp sử dụng kết thúc.

#### Thẻ công đã được nộp
Nếu trong Dòng chính, thẻ công hiện tại của Nhân viên đã được nộp, hệ thống sẽ hiển thị bản sao chỉ đọc của thẻ công và thông báo cho Nhân viên rằng thẻ công đã được nộp, vì vậy không thể thực hiện bất kỳ thay đổi nào đối với nó. Nhân viên xác nhận thông báo và trường hợp sử dụng kết thúc.

#### Cơ sở dữ liệu Quản lý Dự án không khả dụng
Nếu trong Dòng chính, Cơ sở dữ liệu Quản lý Dự án không khả dụng, hệ thống sẽ hiển thị thông báo lỗi cho biết danh sách các mã dự án có sẵn không khả dụng. Nhân viên xác nhận lỗi và có thể chọn tiếp tục (không có mã dự án có thể chọn) hoặc hủy (bất kỳ thay đổi thẻ công nào cũng bị loại bỏ và trường hợp sử dụng kết thúc).
Lưu ý: Nếu không có mã dự án có thể chọn, Nhân viên có thể thay đổi giờ cho một mã dự án đã được liệt kê trên thẻ công, nhưng họ không thể thêm giờ cho một mã dự án chưa được liệt kê.
## Special Requirements  
Không có.
## Pre-Conditions 
Nhân viên phải đăng nhập vào hệ thống trước khi trường hợp sử dụng này bắt đầu.
## Post-Conditions 
Nếu trường hợp sử dụng thành công, thông tin thẻ công của Nhân viên được lưu vào hệ thống. Nếu không, trạng thái hệ thống không thay đổi.
## Extension Points 
Không có.

# 7.Run Payroll 
## Brief Description 
Trường hợp sử dụng này mô tả cách chương trình tính lương được chạy vào mỗi thứ Sáu và ngày làm việc cuối cùng của tháng.
## Flow of Events 
### Basic Flow 
1. Trường hợp sử dụng bắt đầu khi đến lúc chạy chương trình tính lương. Chương trình tính lương được chạy tự động vào mỗi thứ Sáu và ngày làm việc cuối cùng của tháng.
2. Hệ thống truy xuất tất cả nhân viên nên được trả lương vào ngày hiện tại.
3. Hệ thống tính toán lương bằng cách sử dụng thẻ công đã nhập, đơn đặt hàng, thông tin nhân viên (ví dụ: lương, phúc lợi, v.v.) và tất cả các khoản khấu trừ hợp pháp.
4. Nếu phương thức giao lương là gửi thư hoặc nhận trực tiếp, hệ thống sẽ in phiếu lương.
5. Nếu phương thức giao lương là chuyển khoản trực tiếp, hệ thống sẽ tạo một giao dịch ngân hàng và gửi nó đến Hệ thống Ngân hàng để xử lý.
6. Trường hợp sử dụng kết thúc khi tất cả nhân viên nhận lương cho ngày mong muốn đã được xử lý.
### Alternative Flows 
#### Hệ thống Ngân hàng không khả dụng
Nếu Hệ thống Ngân hàng không hoạt động, hệ thống sẽ cố gắng gửi lại giao dịch ngân hàng sau một khoảng thời gian xác định. Hệ thống sẽ tiếp tục cố gắng gửi lại cho đến khi Hệ thống Ngân hàng khả dụng.

#### Nhân viên đã xóa
Sau khi lương của Nhân viên được xử lý, nếu nhân viên đã được đánh dấu để xóa (xem trường hợp sử dụng Duy trì Nhân viên), thì hệ thống sẽ xóa nhân viên.
## Special Requirements  
Không có.
## Pre-Conditions
Không có.
## Post-Conditions 
Thanh toán cho mỗi nhân viên đủ điều kiện được trả lương vào ngày hiện tại đã được xử lý.
## Extension Points 
Không có.

# 8.Select Payment Method 
## Brief Description 
Trường hợp sử dụng này cho phép Nhân viên chọn phương thức thanh toán. Phương thức thanh toán kiểm soát cách Nhân viên sẽ được trả lương. Nhân viên có thể chọn nhận lương trực tiếp, nhận lương qua thư hoặc chuyển khoản trực tiếp vào tài khoản ngân hàng được chỉ định.
## Flow of Events 
### Basic Flow 
Trường hợp sử dụng này bắt đầu khi Nhân viên muốn chọn phương thức thanh toán.

1. Hệ thống yêu cầu Nhân viên chỉ định phương thức thanh toán mà họ muốn (nhận trực tiếp, qua thư hoặc chuyển khoản trực tiếp).
2. Nhân viên chọn phương thức thanh toán mong muốn.
3. Nếu Nhân viên chọn phương thức thanh toán "nhận trực tiếp", không cần thông tin bổ sung.
- Nếu Nhân viên chọn phương thức thanh toán "qua thư", hệ thống yêu cầu Nhân viên chỉ định địa chỉ để gửi phiếu lương.
- Nếu Nhân viên chọn phương thức "chuyển khoản trực tiếp", hệ thống yêu cầu Nhân viên chỉ định tên ngân hàng và số tài khoản.
4. Sau khi Nhân viên cung cấp thông tin yêu cầu, hệ thống cập nhật thông tin Nhân viên để phản ánh phương thức thanh toán đã chọn.
### Alternative Flows 
#### Nhân viên không tìm thấy
Nếu trong Dòng chính, thông tin về nhân viên không thể được tìm thấy, hệ thống sẽ hiển thị thông báo lỗi và trường hợp sử dụng kết thúc.
## Special Requirements
Không có.
## Pre-Conditions 
Nhân viên phải đăng nhập vào hệ thống trước khi trường hợp sử dụng này bắt đầu.
## Post-Conditions 
Nếu trường hợp sử dụng thành công, phương thức thanh toán cho Nhân viên được cập nhật trong hệ thống. Nếu không, trạng thái hệ thống không thay đổi.
## Extension Points 
Không có.
