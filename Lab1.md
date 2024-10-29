Kết quả bài thực hành Lab1:
#3. Phân tích ca sử dụng Select Payment:
- Các lớp phân tích:
  + boundary: PaymentForm
  + control: PaymentController
  + entity: EmployeeEntity
- Biểu đồ tuần tự:
  ![Diagram](https://www.planttext.com/api/plantuml/png/j9J1IiD048Rl-nH3Jote2_GWXLBrwDNZkWtTq6HssMmEEOed4G--GQk8M2ZKeycXXvM-Hvx0Lt3Iq9hIfgBK71B-PUURVtw6V6RpJcIviN4Oi6Ze8nWLUOnnOPM1NgW3bNWUkr8nzhb9u88deOVsL9cG2ONMg61rrYrbu1b6ohV9khotb8ojD1oVL47GXgxCiti4BHUpnHW7O4c_2lfmb62L6sEpnQebH5ZJsd3kvzaDBglkmBht14G9t0GSjl_MsCGvoxEfJrSP3smT56MUJf41FTk8obnbQeKvkg_BChlF8ZGR9RlHObuGUNK61eL94ejPlOdDU2xT90QHfoynV3nGndoPxss5H3CNh3q9nsI04C_w1yJ1C_dkK9UBbcwiLqvebQvfSKoUlOb2fNFzXvY4zCjY2pXmZmZIZQXJqxe9La-EQ5r7FWobojCd_4M8knlySuOxiYaonJvZ7NhJF-GB003__mC0)
- Nhiệm vụ của từng lớp phân tích:
  + Boundary
    PaymentForm: Đây là lớp giao diện mà nhân viên sử dụng để chọn phương thức thanh toán. PaymentForm sẽ yêu cầu nhân viên nhập phương thức thanh toán mong muốn, bao gồm các tùy chọn như "Pick Up", "Mail", và "Direct Deposit”.
  + Control
    PaymentController: Điều khiển và xử lý logic của quy trình chọn phương thức thanh toán, nhận yêu cầu từ PaymentSelectionForm, xử lý và tương tác với các lớp Employee, PaymentMethod, và Database để cập nhật phương thức thanh toán của nhân viên.
  + Entity
    EmployeeEntity: Chứa thông tin nhân viên như ID, tên và thông tin thanh toán hiện tại.
- Thuộc tính và quan hệ giữa các lớp phân tích:
 + PaymentForm (Boundary)
  Thuộc tính:
    selectedPaymentMethod: String – Phương thức thanh toán được chọn (có thể là "pick up", "mail", hoặc "direct deposit").
    address: String – Địa chỉ nhận thư (chỉ dùng khi phương thức thanh toán là "mail").
    bankName: String – Tên ngân hàng (chỉ dùng khi phương thức thanh toán là "direct deposit").
    accountNumber: String – Số tài khoản ngân hàng (chỉ dùng khi phương thức thanh toán là "direct deposit").
  Quan hệ:
    Tương tác với PaymentController để gửi thông tin lựa chọn thanh toán từ nhân viên.

+ PaymentController (Control)
  Thuộc tính:
    controllerId: int – Mã định danh cho PaymentController.
    Phương thức:
    processPaymentMethodSelection(): Xử lý lựa chọn phương thức thanh toán từ PaymentForm.
    updatePaymentInfo(): Cập nhật thông tin thanh toán của nhân viên dựa trên lựa chọn phương thức thanh toán.
  Quan hệ:
    Nhận dữ liệu từ PaymentForm để xử lý thông tin lựa chọn thanh toán.
    Tương tác với Database để lưu thay đổi thông tin thanh toán của Employee.
    Cập nhật thông tin về phương thức thanh toán trong lớp PaymentMethod

+ Employee (Entity)
  Thuộc tính:
    employeeId: int – Mã định danh nhân viên.
    employeeName: String – Tên nhân viên.
    address: String – Địa chỉ của nhân viên.
    paymentClassification: String – Loại hình thanh toán (theo giờ, cố định, hoa hồng).
  Quan hệ:
    Liên kết với PaymentMethod để lưu trữ thông tin về phương thức thanh toán hiện tại của nhân viên.
    Tương tác với PaymentController để cập nhật lựa chọn thanh toán.
- Biểu đồ lớp:
  ![Diagram](https://www.planttext.com/api/plantuml/png/R59DJiGW5DvpYYvrmGLcDOdHP1QEnfxW5LuT8l08F1QDyMGkF99NaBPasavbn_Sz-7xWz_ldc1WYPsU5K1PIQbvXSEZvYQ9hFaLJLaABYb5NvXdvGlhGj1oDVvycGEk8AMsm3lp76Hnk1vMYxFcSNOTnnKWvqTgaO66eGY-13VbqTp-xo9qpt4vU2bpGhnlB3-GvahKOgt5r1Kx5h_6yA8L8gZZUH5hVFSxae86nZfnyJslDHnSi3OXL2kjs4LgmVGl_r1LgXl5oqni5ev6RGXEsO24EXwQt15mpEcVA4V9lnUoQkL2ETjYYDVqcsHn-pYRMho_blbYnXwIybY744Rqkd-aF003__mC0)

- Giải thích:
  + PaymentForm: Lớp giao diện người dùng để nhân viên lựa chọn phương thức thanh toán. Nó chứa các thuộc tính để lưu trữ thông tin lựa chọn và các phương thức để hiển thị tùy chọn và gửi lựa chọn.
  + PaymentController: Lớp điều khiển logic xử lý thông tin từ PaymentForm. Nó xử lý việc lựa chọn phương thức thanh toán và cập nhật thông tin thanh toán của nhân viên.
  + Employee: Lớp thực thể đại diện cho nhân viên trong hệ thống. Nó lưu trữ thông tin nhân viên và có phương thức để cập nhật phương thức thanh toán.
