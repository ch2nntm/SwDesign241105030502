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
   ![Diagram](https://www.planttext.com/api/plantuml/png/X5J1RjD04BtlLyonbU07Sa0LRaAb9bKbzm37pSR4flQwsEj8lXLnu50Xb0C792eI8eHK4L442Cbxw66Z_iVs1_W5PktOJfm0FbZMp7kpyzxC-hUysOi5ZKGI-2G-zJX4OUmGoaGOGJiuyyFKSO36q2RzCE436gLWHGuLJfdiX55W05QxKqDiEgeITeUma8iez1jCguZwJbJmBU9muOdc0KMI3AYWVHexS1o5pnmcUfJJeHCWPR_C8F2ujqz86-u_CFsqeAVb1tXg6X4wcuRGL_XY-DhP9GWmk7OBdgYh19ZEFYV0NPtDpq1uUSXLypLANVXe0xVZXtY4L-Fl0H-gIGfzdNqLi1YR-cNiL6St0eIhChPB2FK5F2nfS7V-_aJBjtm8Gq_BI_3L980HVhvYU588WPRl10oq_0Pgok_EBmdWirI3BhRWaPPp3z9QbQ-pJoa4QbRHK4p1iWmBNMj1jm8nzHrYdVqiKPYkQfz4Efl1ICiNCA3SXLXDcVkFqhbR1zZzIuvwjRpu3wsss4BqQzx4E7n0oAROlmoiQW8RNry0oBFRP6tbDqNKTSn8ZbpraUECr9LfCPzdz_OwgL6rDBkpjc_-6cpfWLqkPhbbM1T6QcBwkm0HeKZ3MtNCb7sCdXOBRBfKFt2315xe5QYzOTjMs8fhtTLeHQwNTJ76yIp6jzTQpjYM6dRJkEM9kUHSF0Ock13CXCryVRp8XmN8t_HmfRM3HCjVUBlacyPQOEwmlb_mF4cDPr-uI_OGXZ-wFm000F__0m00)
   ### 1.2.Login:
   ### 1.3.Maintain Purchase Order:
   ### 1.4.Create Administrative Report:
   ### 1.5.Maintain Employee Info:
   ### 1.6.Run Payroll:
 ## 2.Viết code Java mô phỏng ca sử dụng Maintain Timecard:
