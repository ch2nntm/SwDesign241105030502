# Bài thực hành Lab2
 ## 1.Tiến hành phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System:
   ### 1.1.Create Employee:
   #### - Các lớp phân tích:
    +) Entity: CreateEmployee, ProjectManagementDatabase
    +) Boundary: CreateEmployeeForm, SaveForm
    +) Control: CreateEmployeeController
   #### - Biểu đồ tuần tự:
   ![Diagram](https://www.planttext.com/api/plantuml/png/X5J1RjD04BtlLyonbU07Sa0LRaAb9bKbzm37pSR4flQwsEj8lXLnu50Xb0C792eI8eHK4L442Cbxw66Z_iVs1_W5PktOJfm0FbZMp7kpyzxC-hUysOi5ZKGI-2G-zJX4OUmGoaGOGJiuyyFKSO36q2RzCE436gLWHGuLJfdiX55W05QxKqDiEgeITeUma8iez1jCguZwJbJmBU9muOdc0KMI3AYWVHexS1o5pnmcUfJJeHCWPR_C8F2ujqz86-u_CFsqeAVb1tXg6X4wcuRGL_XY-DhP9GWmk7OBdgYh19ZEFYV0NPtDpq1uUSXLypLANVXe0xVZXtY4L-Fl0H-gIGfzdNqLi1YR-cNiL6St0eIhChPB2FK5F2nfS7V-_aJBjtm8Gq_BI_3L980HVhvYU588WPRl10oq_0Pgok_EBmdWirI3BhRWaPPp3z9QbQ-pJoa4QbRHK4p1iWmBNMj1jm8nzHrYdVqiKPYkQfz4Efl1ICiNCA3SXLXDcVkFqhbR1zZzIuvwjRpu3wsss4BqQzx4E7n0oAROlmoiQW8RNry0oBFRP6tbDqNKTSn8ZbpraUECr9LfCPzdz_OwgL6rDBkpjc_-6cpfWLqkPhbbM1T6QcBwkm0HeKZ3MtNCb7sCdXOBRBfKFt2315xe5QYzOTjMs8fhtTLeHQwNTJ76yIp6jzTQpjYM6dRJkEM9kUHSF0Ock13CXCryVRp8XmN8t_HmfRM3HCjVUBlacyPQOEwmlb_mF4cDPr-uI_OGXZ-wFm000F__0m00)  
   #### - Thuộc tính và phương thức của các lớp:
     CreateEmployeeForm:(Boundary)
      - Thuộc tính:
        reportType: String
        beginDate: Date
        endDate: Date
      - Phương thức:
        getReportCriteria()
        displayReportOptions()
        displayErrorMessage(message: String)
     SaveForm:(Boundary)
      - Thuộc tính:
        saveName: String
        saveLocation: String
      - Phương thức:
        promptForSaveDetails()
        confirmSave()
        displaySaveSuccessMessage()
     CreateEmployeeController:(Control)
      - Phương thức:
        createReport(criteria: ReportCriteria): EmployeeReport
        saveReport(report: EmployeeReport, saveName: String, saveLocation: String)
        handleMissingInformation()
        validateCriteria(criteria: ReportCriteria)
     CreateEmployee:(Entity)
      - Thuộc tính:
        reportID: int
        content: String
        reportType: String
        beginDate: Date
        endDate: Date
        chargeNumber: String
      - Phương thức:
        generateContent()
        saveToFile(name: String, location: String)
        discard()
     ProjectManagementDatabase(Entity)
      - Phương thức:
        getAvailableChargeNumbers(): List<String>
   #### - Mối quan hệ giữa các lớp phân tích:
     Employee tương tác với EmployeeReportForm để nhập tiêu chí báo cáo.
     EmployeeReportForm thu thập thông tin và chuyển cho EmployeeReportController xử lý.
     ReportSaveForm thu thập thông tin liên quan đến việc lưu báo cáo.
     EmployeeReportController tạo báo cáo bằng cách sử dụng EmployeeReport và có thể truy xuất mã dự án từ ProjectManagementDatabase.
     EmployeeReport chịu trách nhiệm tạo nội dung báo cáo, lưu file, hoặc hủy bỏ báo cáo.
   #### - Biểu đồ lớp:
   ![Diagram](https://www.planttext.com/api/plantuml/png/f9DDRi8m48NtEOMNxO8BiAYe0aX8XLQ52qoS8RZrJpGsIAZgoRheaNg5Zd63afIm8GjBUIz-_cR6-VdwdlW05FP6P_vTMK7EOvP93TwBd102paojtH5nxiY8ZqpmCoAi7ONDiSQnM0TIjafwWPMoKzuq5d5D8jgo9uaAm-if8YSLa1JStIUZLBxMS4pcSnsKixxdpOWSBT5xg92jpuPs3OSEe-Vt5PWUOLIVd8IOt754JSxKWHDYq1G3A7q-MZgxLMIYqwE9qdel9VDSOEfsC7SsaDCQwOzHo9EVgcs28s5NsO4jDIwLzmoxi5ikyiJV-0VGgkISLZC72BhpMqp7GjcG92une0tTRjquvv7S0LMusfi2gTlj2YrIP4x7jelVkBdIxJvBeB9TqmkvDvHX2PRRRNWt7mW5-AQyUBqU3pm_A3JcBGIVKYxSwz73uAoomI7-stJrqq7gx7nphr5CkBtyb_u2003__mC0)
   
   ### 1.2.Login:
   #### - Các lớp phân tích:
    +) Boundary: LoginEmployeeForm, LoginAdminForm
    +) Control: LoginController
    +) Entity: User
   #### - Biểu đồ tuần tự:
   ![Diagram](https://www.planttext.com/api/plantuml/png/p9IzJiCm4CTtFyMDCF027H1Mb894G1tem1ZIWAqwTfKubJ8pCB30nCZNW41qGq9AXWxfY_W9U0NE2QNXer3401aY--xdkt_EV-Mf6Aybsezr6WcIzBc4M2KXyGEjOd2ZWL1P68AVWFiIw_XPh8IWlOXBdkZOjq7CToZPKwdi-N46dZhWSdguhUB80fxRVaTKDLxJj4q29JKMhxDElH5XLTvpI2WrrnbqaphI9SI5bLLRjmLRfZY7VLjgSZevb0SWcSb70mYOmcLv9M78opj94BPdt1RibdSf12Q_IQUiHW26vGL4kDNGn-XjskYn_HKshUmvBLWtnOZFuJp7KjqMR79J74Q00qHo91amKrmFG9ZYQ6cP-4B33YiVy4iqtiaiHm2VxhJJVAJkK-cUd3GdebbvWTq2Ux0cNqVYi3H3KH9dQFAnX0X9OEMznPdLI4AHXCsc_NgvWBpFoORA3LwrraWSMv6MtYilbONF-3kb7ozFcFnopio1APC_1hRtJVRM7-Yf7Y4TMgcWF_4HhQHqwE96QdJvnadqFpg9Bk2asL3-p4fqGIjzTN-_yD8Qll1F-Wm00F__0m00)
   #### - Thuộc tính và phương thức của các lớp:
   LoginEmployeeForm:(Boundary)
     - Thuộc tính:
       username: String: Lưu tên người dùng đã nhập.
       password: String: Lưu mật khẩu đã nhập.
     - Phương thức:
       displayForm(): Hiển thị giao diện form đăng nhập.
       getInput(): Lấy tên người dùng và mật khẩu từ giao diện.
       showError(message: String): Hiển thị thông báo lỗi nếu đăng nhập thất bại.
       showSuccess(): Hiển thị giao diện chính khi đăng nhập thành công.
   LoginAdminForm: (Boundary)
     - Thuộc tính:
       username: String: Lưu tên người dùng đã nhập.
       password: String: Lưu mật khẩu đã nhập.
     - Phương thức:
       displayForm(): Hiển thị giao diện form đăng nhập.
       getInput(): Lấy tên người dùng và mật khẩu từ giao diện.
       showError(message: String): Hiển thị thông báo lỗi nếu đăng nhập thất bại.
       showSuccess(): Hiển thị giao diện chính khi đăng nhập thành công.
   LoginController: (Control)
     - Thuộc tính:
       user: User: Lưu đối tượng người dùng (Employee hoặc Admin).
     - Phương thức:
       validateCredentials(username: String, password: String): boolean: Kiểm tra tính hợp lệ của tên người dùng và mật khẩu.
       loginUser(): void: Thực hiện quá trình đăng nhập và chuyển hướng người dùng nếu thông tin hợp lệ.
       showErrorMessage(message: String): Hiển thị thông báo lỗi khi tên người dùng hoặc mật khẩu không hợp lệ.
   User: (Entity)
     - Thuộc tính:
       username: String: Lưu tên người dùng.
       password: String: Lưu mật khẩu của người dùng.
     - Phương thức:
       getUsername(): String: Lấy tên người dùng.
       getPassword(): String: Lấy mật khẩu của người dùng.
       setUsername(username: String): void: Đặt tên người dùng.
       setPassword(password: String): void: Đặt mật khẩu người dùng.
   #### - Mối quan hệ giữa các lớp phân tích:
   LoginEmployeeForm và LoginAdminForm sẽ gọi đến LoginController để xác thực thông tin người dùng.
   LoginController sẽ tương tác với User để kiểm tra tính hợp lệ của tên người dùng và mật khẩu, và sẽ trả kết quả về lại cho LoginEmployeeForm hoặc LoginAdminForm.
   LoginController không trực tiếp lưu trữ thông tin người dùng mà chỉ thao tác với đối tượng User để xác thực.
   User là một lớp chứa thông tin về người dùng (bao gồm tên và mật khẩu), cung cấp các phương thức lấy và thiết lập giá trị của các thuộc tính này.
   #### - Biểu đồ lớp:
   ![Diagram](https://www.planttext.com/api/plantuml/png/p991QWCn34NtFeMMpM8ka4L92IaKMYY47C2CnSHKbWV9qn1AJjP5ZzGhr0ucdPbarLMzyEBnfVyb-_lpQwN9IXe26Ntp318LJKjM5PvZvtaJUef7nCSe0JuCvDF0e2Xi0ovXcyHpLt6VgmvHt0G3EAyzsMFfSBUehCFqnFsGBa3tyR0HYJ8Xsw5jKJMpancdUd31y_-Aj8wS91AXJ38jOPVlMlzkoJkRS2tea9Etf9VUL9eKxRN_I_Qp7OujY_2Fi-SvTxLWFFjhLV_Qtz3fH9VJNF-HfhcVByJCtko61CmS5D5vTIjabx_d3m000F__0m00)
   
   ### 1.3.Maintain Purchase Order:
   #### - Các lớp phân tích:
   #### - Biểu đồ tuần tự:
   #### - Thuộc tính và phương thức của các lớp:
   #### - Mối quan hệ giữa các lớp phân tích:
   #### - Biểu đồ lớp:
   
   ### 1.4.Create Administrative Report:
   #### - Các lớp phân tích:
   #### - Biểu đồ tuần tự:
   #### - Thuộc tính và phương thức của các lớp:
   #### - Mối quan hệ giữa các lớp phân tích:
   #### - Biểu đồ lớp:
   
   ### 1.5.Maintain Employee Info:
   #### - Các lớp phân tích:
   #### - Biểu đồ tuần tự:
   #### - Thuộc tính và phương thức của các lớp:
   #### - Mối quan hệ giữa các lớp phân tích:
   #### - Biểu đồ lớp:
   
   ### 1.6.Run Payroll:
   #### - Các lớp phân tích:
   #### - Biểu đồ tuần tự:
   #### - Thuộc tính và phương thức của các lớp:
   #### - Mối quan hệ giữa các lớp phân tích:
   #### - Biểu đồ lớp:
   
 ## 2.Viết code Java mô phỏng ca sử dụng Maintain Timecard:
