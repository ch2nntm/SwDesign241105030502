# Bài thực hành Lab2
 ## 1.Tiến hành phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System:
   ### 1.1.Create Employee:
   #### - Các lớp phân tích:
   +) Entity: CreateEmployee, ProjectManagementDatabase
   +) Boundary: CreateEmployeeForm, SaveForm
   +) Control: CreateEmployeeController
   #### - Biểu đồ tuần tự:
     
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
   ### 1.3.Maintain Purchase Order:
   ### 1.4.Create Administrative Report:
   ### 1.5.Maintain Employee Info:
   ### 1.6.Run Payroll:
 ## 2.Viết code Java mô phỏng ca sử dụng Maintain Timecard:
