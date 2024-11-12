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
    +) Boundary: MaintainPurchaseOrderForm
    +) Control: MaintainPurchaseOrderController
    +) Entity: PurchaseOrder, PurchaseOrderDatabase
   #### - Biểu đồ tuần tự:
   ![Diagram](https://www.planttext.com/api/plantuml/png/x5RDQjj04BxlKymn0UK5V2Z1FssWlmSVtEDQ5f68j1AhLR6E9OTIIg4vzDIBJIWbWK2XXO94oK4cxx5Fq5VexCgrToFPSKgFDTYBTcU-cVdccvL_bTU7gQ1SP558qfE00OzJZr1Nn1m6KHB6kUS1JM50nd769fJdy9G6JE3tHSPTdwRUSpxn-CEOHyfEhSIDcU1ns6xPgmz3ZolxzHFnc0X43fPnwsQV2Zh61-NVxn8oW8C7Ed07UhuitpDmSRbmWIrEsJ7i3MKnZnteoU8g0URZ8XmOLT_eFj5fe_SwZGwCP7a5OVKJykeo0rSMNp8Ba10Q2j2WiFXmCsTmLCrm6_1Z5BVAwUKQHWTFGFZLTqnC8DsBCmNWhm2CMfurZFV2eBf4Qrc-WHE_chj-xUaWZ2pVKPtcMmTIMPmpID3_8dA07LUpV5-ZjvNx2CiDjgLarsHrehEa8PBbfs191gPI_126l-MX8FhT3Zov-PgPGRLblmi7pH1_J6VC1rSvjAEQDGqvCW2lPFaQekhyZefgjey2MPuoZ8D4tdQgwxCO7A3MCZp1ldvE6a685w8yQy7fDehxAkLs1cgNgT-LX3V8fQtUpMs_cntLh27FSfXcMAgmaXA-5oi8itaRsh2plbgwiTkucEDjkjJC2P_cUae-1hjFGeFkhQDW9V0Nis0dU9zPQ6DmXDT3dOnTX-rT2rNTXVz6e5D4-YzC-vumI9iQJMcZQjHslfcat4HUMc-LgD7etQIf7RReKP_lfCTXpTMuKc_DC-pkjE7giGaX1d6FPN6jzLguQZnY44WFEKGp_BVo6m00__y30000)
   #### - Thuộc tính và phương thức của các lớp:
    MaintainPurchaseOrderForm: (Boundary)
      - Thuộc tính:
        customerContact: String
        customerAddress: String
        productList: List<Product>
        orderDate: Date
      - Phương thức:
        getInputData(): PurchaseOrder
        displayOrderDetails(order: PurchaseOrder)
        confirmDeletion(): Boolean
    MaintainPurchaseOrderController: (Controller)
      - Phương thức:
        createOrder(order: PurchaseOrder)
        updateOrder(orderID: String, updatedOrder: PurchaseOrder)
        deleteOrder(orderID: String)
        getOrder(orderID: String): PurchaseOrder
    PurchaseOrder: (Entity)
      - Thuộc tính:
        orderID: String
        customerContact: String
        customerAddress: String
        productList: List<Product>
        orderDate: Date
        commissionedEmployeeID: String
        status: String (Open/Closed)
      - Phương thức:
        isOrderOpen(): Boolean
        belongsToEmployee(employeeID: String): Boolean
    PurchaseOrderDatabase
      - Phương thức:
        saveOrder(order: PurchaseOrder)
        updateOrder(order: PurchaseOrder)
        deleteOrder(orderID: String)
        findOrder(orderID: String): PurchaseOrder
   #### - Mối quan hệ giữa các lớp phân tích:
    PurchaseOrderController điều khiển các thao tác nghiệp vụ liên quan đến PurchaseOrder và tương tác với PurchaseOrderDatabase để lưu trữ thông tin.
    PurchaseOrder có Product (thể hiện mối quan hệ chứa nhiều - aggregation).
    MaintainPurchaseOrderForm tương tác với PurchaseOrderController để gửi yêu cầu.
   #### - Biểu đồ lớp:
   ![Diagram](https://www.planttext.com/api/plantuml/png/n5HHJiCm3FtlAVAvIUm24ve65AH9e4s22sIDDoAIkB8Jf0bnCZuu4bSWwRf1IXcm7oerKcs_P_lPwTlBwvIz91-iAVX1Eq7888gYCf9Pt4ZjV7mNWQfxoJ0d1NI5PCLJ8U8p4bLWZnRe0cDWvSVYrfDswuxtJ2a2vewt9bIXyjUQ8owTfukjPT86O4fNIWzZaSx6AiGQ_CpLmKUJ70p78YkkZL6QQoCtZQc4s8BXGSFM2H-syHMwbIPRWW6lqINQSqG3qXNF1yL8VHCQ0zHA4ha8Oh6Dzs3EKAiyRbRk13ffdMf-0AzIiVtuuOTK_VwkQlicC_D-oXtuVyq-agArcZcE2DIbhGrk0BxK5HVQXpoX49gRbkOrPDFTEfTWqAtv3dUS0_X2thSIcLff7vVnOxy8B1-FMOFZnxtIJlrstjzVxT5eyjEkzwC_tON4aMVyCs8dPp45f-BlwHq00F__0m00)
   ### 1.4.Create Administrative Report:
   #### - Các lớp phân tích:
    +) Boundary: CreateAdministrativeReportForm
    +) Control: CreateAdministrativeReportController
    +) Entity: AdministrativeReport
   #### - Biểu đồ tuần tự:
   ![Diagram](https://www.planttext.com/api/plantuml/png/j9F1Qi9048Rl-nHpLB0luA4O0j93AH9wiCSO5xEuxfRDHCYnz2Yb-0PQ4K6Gzj1JGkbXIzzZdw2lqDse6AdjhJc4CFbd_c_-JRwAzrQ2eS9qn4aoP0AKJ2W98vGAEc6c9ETUVyG4Ir25hXWcqF58JwQY7weCV4L3f1K96zE0tag5RQb6JkrxGPj4Kg2TzOVStoeuLRicdr2133CufNOQBo2auy7PUMdHX1kzJY4o-Ig5dfvBYDojngN9v-nGQO0Ow5a6FPC_8tnCdNvV6vhy7G5ZdKSDGBqM86Bz963Cx7ETE1jdr_6QS1MRV7CBo4hJM6yE3aTGVYe63chvYtO_qotSX6lBAl-FtZzmNIkJBs1iYhkJ-HxjUi5CSI_iP5DCAd0VKxq0TCGav6YLTZTJF0ZWdo-L8o1WhseabqUleUPG6mvb0gZqfbusxFszODTGEuLPQTkkl6tsWeDRLyyZ6uGzhIqOeJoXZcSOwrTxDcNjX-CkTbCydZR-syV6iChARliDzu-ox9fY0ro_LGA8fPu95-GIISlgtQ_u3G00__y30000)
   #### - Thuộc tính và phương thức của các lớp:
    CreateAdministrativeReportForm: (Boundary)
      - Thuộc tính:
        reportType: Loại báo cáo cần tạo (e.g., "Total Hours Worked", "Pay Year-to-Date").
        startDate, endDate: Khoảng thời gian báo cáo.
        employeeName: Tên nhân viên (nếu cần lọc theo nhân viên).
      - Phương thức:
        enterReportCriteria(): Cho phép Payroll Administrator nhập tiêu chí báo cáo.
        submitReportRequest(): Gửi yêu cầu tạo báo cáo.
        displayGeneratedReport(): Hiển thị báo cáo đã tạo.
        saveReport(): Lưu báo cáo với tên và vị trí chỉ định.
        discardReport(): Hủy bỏ báo cáo đã tạo.
    CreateAdministrativeReportController: (Control)
      - Phương thức:
        createReport(): Tạo báo cáo dựa trên các tiêu chí đã cung cấp và trả về một đối tượng AdministrativeReport.
        validateCriteria(): Xác thực tiêu chí báo cáo trước khi tạo.
    AdministrativeReport: (Entity)
      - Thuộc tính:
        id: Mã định danh báo cáo.
        reportContent: Nội dung báo cáo.
        generatedDate: Ngày tạo báo cáo.
        reportType: Loại báo cáo.
        startDate, endDate: Khoảng thời gian báo cáo.
        employeeName: Tên nhân viên (nếu có).
      - Phương thức:
        save(): Lưu báo cáo vào vị trí chỉ định.
        discard(): Hủy bỏ báo cáo.
        generateContent(): Tạo nội dung cho báo cáo dựa trên các tiêu chí.
   #### - Mối quan hệ giữa các lớp phân tích:
    CreateAdministrativeReportForm là lớp trung gian nhận và gửi thông tin, giao tiếp với CreateAdministrativeReportController để tạo báo cáo và AdministrativeReport để lưu hoặc hủy báo cáo.
    CreateAdministrativeReportController thực hiện logic tạo báo cáo và trả về đối tượng báo cáo cho CreateAdministrativeReportForm.
    AdministrativeReport lưu trữ nội dung và thực hiện các thao tác liên quan đến lưu trữ hoặc hủy bỏ báo cáo.
   #### - Biểu đồ lớp:
   ![Diagram](https://www.planttext.com/api/plantuml/png/Z5DBJeL04DnpYbdgOYx0mZo3qPsBfnUOntHUEiu7UneIOZoP2u_a5Hm6y0r8H1PaqbDLtLq5Nn-VXy2AkBMc22_e1Fa0HL4R5OAe21J3hRReC30fnWwEq7ZYUqzMl1KYFfGAptq3fNXYGdTEvQHw5-cb6Dwf1awlAxOnlWTuL3QdIpdX6MXiM176Cwghwr9q7lNOeprPv15mXDSM0Y_kDOR6gFu17CJXGO_8fOIQLrepQqLhmlk-CPLtJDuOeCcUEa4lGbka1EoKGHsX-QOdxmqeTscynKwDf41T2dISplGpIxGmzrMSPoyMGSZj5EL6Yl9NYd8dnS7YV9dCttLvdcwQF3T-vrkCpMx-5SiVGbbsWzfcKeUuVVnNlW400F__0m00)
   
   ### 1.5.Maintain Employee Info:
   #### - Các lớp phân tích:
    +) Boundary: MaintianEmployeeInfoForm
    +) Control: MaintainEmployeeInfoController
    +) Entity: Employee
   #### - Biểu đồ tuần tự:
   ![Diagram](https://www.planttext.com/api/plantuml/png/l5H1IiD05DtFAVvI8Ng0BgGbHkb2ATX5jsCQpM0oKoQJOfRYIaImQpUj8c9141I4PE4YfVUO4tW5_wHLessb81Z8JFXvxx__teIyPQ_LI56fuZ0WqH7Z84Na4Ueg8Q514oc2eDOE6MUHajGKQGID6jaNCMzJcS0EPLpXxOITG2IUL-S7Oal8qE1sdFeMSGLNs6Kkq9wy2pmvXTl4uugf13vGfkuGqgZ1saRHhmAshxCB3YvkzoxmqIa_X9Mcdmz32soTFdI0-xWf2rhv4rqbXZLbsnNOrja3WoGVnk3gz2u6PPX8oQyvT5a-v8JGG47Ha01UXlUblkiN4iXwHbs5WPMfKtn9puuHXagtYpWuEwuMZ7ewEwU5hJCB8ftrO6zlruBkUdTzzTiWJWMQEXq827LsnMRqdI_nLZvm9sdmEJvdpOqkTVgYeEEF7yS3C-eauyCYCyLqTeBSl0zAwlG60Xo2bLtXOv_xu9e27cHxacJvJ1O7Mj_yQv0_Cohh_aPPa9Vx-zZD-H6CUldDT-fd3kPh_4__HczPiyVpi4iPBfYp1r_55Nyfxm000F__0m00)
   #### - Thuộc tính và phương thức của các lớp:
    MaintainEmployeeInfoForm (Boundary)
      - Thuộc tính:
        employeeName: Tên của nhân viên.
        employeeAddress: Địa chỉ của nhân viên.
        employeeSSN: Số an sinh xã hội của nhân viên.
        employeePhoneNumber: Số điện thoại của nhân viên.
        employeeSalary: Lương của nhân viên.
      - Phương thức:
        displayForm(): Hiển thị biểu mẫu để nhập thông tin nhân viên.
        getInputData(): Lấy dữ liệu đầu vào từ quản trị viên (như tên, địa chỉ, số điện thoại...).
        showConfirmation(): Hiển thị thông báo xác nhận thao tác (thêm, cập nhật, xóa).
    MaintainEmployeeInfoController (Control)
      - Thuộc tính:
        actionType: Loại hành động (Thêm, Cập nhật, Xóa).
        employee: Thông tin nhân viên hiện tại đang được xử lý.
      - Phương thức:
        handleAddEmployee(): Xử lý thêm nhân viên mới.
        handleUpdateEmployee(): Xử lý cập nhật thông tin nhân viên.
        handleDeleteEmployee(): Xử lý xóa nhân viên.
        validateEmployeeData(): Xác minh dữ liệu nhân viên hợp lệ trước khi thêm hoặc cập nhật.
        performAction(): Thực hiện hành động được chọn (thêm, cập nhật, xóa).
    Employee (Entity)
      - Thuộc tính:
        employeeID: Mã định danh duy nhất của nhân viên.
        employeeName: Tên của nhân viên.
        employeeType: Loại nhân viên (theo giờ, lương cứng, có hoa hồng).
        salary: Mức lương của nhân viên.
        phoneNumber: Số điện thoại của nhân viên.
        address: Địa chỉ của nhân viên.
      - Phương thức:
        addEmployee(): Thêm nhân viên vào cơ sở dữ liệu.
        updateEmployee(): Cập nhật thông tin nhân viên.
        deleteEmployee(): Xóa nhân viên khỏi cơ sở dữ liệu.
        validateEmployeeInfo(): Kiểm tra tính hợp lệ của thông tin nhân viên.
   #### - Mối quan hệ giữa các lớp phân tích:
    MaintainEmployeeInfoForm gọi MaintainEmployeeInfoController để xử lý các thao tác.
    MaintainEmployeeInfoController tương tác với Employee để thực hiện các thao tác thêm, cập nhật hoặc xóa thông tin nhân viên.
   #### - Biểu đồ lớp:
   ![Diagram](https://www.planttext.com/api/plantuml/png/Z9DDJeH048NtdAAMkk02BCnCH1CM4XFq03LqCNJiltGt6c8ycGkFv1Li40n2Zyw2pNlzeBvwpUVxnyvvjBwJ8d5FN87LZfAa5kWSt25NFZmtqWZT4nMgqRVQIdXD05AWIIvHKWQLjrmTVnbxnYmv5_MggepgzwrML7RoG3QUGu6spo3NtK5Gi00OTqPWFqnsSJagH_A5CftFqUCakLQ_N6lLS2lHSws2_FONPpZhhHQ2x4IBzH1xw4sSDOCvFNwkHSN4i81PdSRurXyDGqzHAoT16-iP1Lyc5bo6R1F0z_KQQZwxAgl8e-EVx703xDO5f61ET8QR_c7GLd1TR1did3KCFOt89ozgcbxzrsuqlF27L_nKkoF5mg_o1G00__y30000)
   ### 1.6.Run Payroll:
   #### - Các lớp phân tích:
   #### - Biểu đồ tuần tự:
   #### - Thuộc tính và phương thức của các lớp:
   #### - Mối quan hệ giữa các lớp phân tích:
   #### - Biểu đồ lớp:
   
 ## 2.Viết code Java mô phỏng ca sử dụng Maintain Timecard:
