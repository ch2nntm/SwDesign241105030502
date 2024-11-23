# Kết quả Lab 4:
## 1.Thiết kế ca sử dụng cho hệ thống Payroll System:
### 1.1 Ca sử dụng: Timecard
- Tác nhân
  + Nhân viên: Tương tác trực tiếp với hệ thống để chấm công và gửi yêu cầu nghỉ phép.
  + Người quản trị hệ thống: Quản lý yêu cầu nghỉ phép và duyệt thông tin thẻ chấm công.
- Hệ thống con
  + TimeCardController: Quản lý việc gửi và lấy dữ liệu thẻ chấm công.
  + ProjectManagementDatabase: Lưu trữ thông tin liên quan đến dự án và thời gian làm việc.
  + TimeCard: Lưu trữ thông tin cụ thể như ID nhân viên, thời gian vào/ra, tổng giờ làm việc, yêu cầu nghỉ phép.

![Diagram](https://www.planttext.com/api/plantuml/png/d9D1IWCn58RtESMZUo_GXLYc8e925xr0EXDcefbao2G3Sm9nsOKh4Lf1n4hHXI1C5Yu2tYCdy0fcXfPEjNN0LNX9tlV-_oVvCXz7kS9IwPIX_99oa28dW72eX8JZD6EY96HL3gAKSZGHcaTObZ2cAGcmZ0B1bHIC4Oa8LrHjJjRrI8eB4gfpp75CKhyvn0fFS4uGMe-0WyCTm3u4YQiUKWZj6uyXfixSGM5d0ls-soRq0Su-N_MkXlhQNZthFfKqyvJFutG8FB7t70fg5xnc-LDFfHwE-RyCIDmfVsoNF07bp8tlofsPhbgPdQLUYJDNOIE5RLosg1qU0rSjC-_ABmeYPrw0rKJTRUR4cIM5qYuqXAvwrC1ZdyKrP8bzolQO-aD8atMBLZXpIq59Lythz1Cxfz0R4HvHNmwoJ8e2inv2pKFiO0zrwJqfI8IhtiCwocS8lTXfMp_Q2_ZnchOYsnROeg4ZhxN-ITy0003__mC0)
    
- Thông tin được lưu trữ
  + ID nhân viên
  + Ngày và giờ vào/ra
  + Tổng số giờ làm việc
  + Yêu cầu nghỉ phép và trạng thái
- Tinh chỉnh mô tả luồng sự kiện:
  + Nhân viên chấm công vào đầu ca làm việc
      Nhân viên đăng nhập vào hệ thống và bắt đầu ca làm việc.
      Hệ thống ghi lại ID nhân viên và thời gian vào ca làm việc.
      Thông tin này được lưu vào TimeCard.
  + Nhân viên tan làm vào cuối ca làm việc
      Vào cuối ca làm việc, Nhân viên chấm công giờ ra.
      Hệ thống tính toán tổng số giờ làm việc của nhân viên dựa trên thời gian vào và ra.
      Hệ thống ghi lại thời gian ra và cập nhật thông tin trong TimeCard.
  + Nhân viên xem lại thẻ chấm công
      Nhân viên có thể xem lại thông tin thẻ chấm công của mình bất cứ lúc nào.
  + Nhân viên gửi yêu cầu nghỉ phép
      Nhân viên có thể gửi yêu cầu nghỉ phép thông qua hệ thống.
      Yêu cầu nghỉ phép sẽ được chuyển tới Người quản trị hệ thống để phê duyệt hoặc từ chối.
  + Quản trị viên duyệt yêu cầu nghỉ phép
      Người quản trị hệ thống xem xét yêu cầu nghỉ phép.
      Người quản trị hệ thống có thể phê duyệt hoặc từ chối yêu cầu nghỉ phép của nhân viên.

### 1.2 Ca sử dụng: RunPayroll
- Tác nhân
  + Người quản trị hệ thống: Khởi động quy trình trả lương.
- Hệ thống con
  + PayrollController: Quản lý toàn bộ quy trình tính lương.
  + IBankSystem và BankSystem: Thực hiện giao dịch gửi lương cho nhân viên.
  + Paycheck: Thực thể chứa thông tin chi tiết về phiếu lương.
  + Employee: Lưu thông tin nhân viên, bao gồm lương và tài khoản ngân hàng.
 
![Diagram](https://www.planttext.com/api/plantuml/png/X5EzJiCm4Dxz53U2H5-W0ofK_0mCI7HWJPqejfASY-DKoiZ4m4kq88HKKGaafcJeO8dty1Fm2bnQqeQs4OiZd---xxlxBj_befSQJviiYLaQIGIjqe0nZnkbuSHF9BAXoj3tT0xNNgvL79yhdG0mhj3GjOxsLzSuqC02DDBaS9QCOfK70QmZbCj5mADDvDJ3QA0zJ8bHAlmJlybJ4oJ0s587T3h7JGbTw0jNJDUoM5DU8tSZh0iNhfnBoEqi0-wALpfN44DNF6C8yTVxrnH3jjjIXLUtquKhLxpaO8Jzf293qb3O9uInj3DawwvRD0mqaS7ObVTDX8DVxYCmTY8X4ggI11XMmC9EC3niaLNFb92f5mKZ8LsnoFvfPclkzMXYLpwW865UTIexHRRjK5szSeTOXIi_E10hbK8eFGM-An-vQ8fd3J_tqWzMenXQwg29OQfo0RnwtIjbpuHlxPIJ9QwOOpjMwp0t-tMfA1yCcMtWBYF3jNr3iRDdo-riowPFPNTj1ki5w5V_sWy0003__mC0)

- Thông tin được lưu trữ:
  + Employee:
      Tên nhân viên
      Lương cơ bản
      Thông tin tài khoản ngân hàng
  + Paycheck:
      ID phiếu lương
      ID nhân viên
      Số tiền lương
      Ngày phát hành
  + Bank Transactions:
      ID giao dịch
      Số tiền
      Thời gian giao dịch
      ID nhân viên
- Tinh chỉnh mô tả luồng sự kiện:
  + Người quản trị đăng nhập và chọn "Run Payroll".
  + PayrollController lấy thông tin nhân viên từ cơ sở dữ liệu Employee.
  + PayrollController tính toán lương và tạo thực thể Paycheck cho từng nhân viên.
  + PayrollController gửi lệnh thanh toán đến IBankSystem.
  + IBankSystem gọi BankSystem để thực hiện giao dịch gửi tiền vào tài khoản nhân viên.
  + BankSystem trả về thông báo giao dịch thành công.
- Tích hợp các hệ thống con
  + TimeCard liên kết với hệ thống quản lý nhân viên để lấy thông tin ID nhân viên.
  + TimeCard tích hợp với hệ thống quản lý nghỉ phép để xử lý các yêu cầu nghỉ.
  + PayrollController tích hợp với TimeCard để lấy dữ liệu giờ làm việc.
  + PayrollController tích hợp với hệ thống ngân hàng để gửi lương cho nhân viên.



