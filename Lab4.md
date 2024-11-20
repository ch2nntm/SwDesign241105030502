Analysis Class	Design Element (Application Layer)	Design Element (Business Services Layer)
LoginForm	LoginForm (UI Component)	-
LoginController	LoginController (Controller for User Login)	UserService (Handles user authentication)
MaintainTimecardForm	MainEmployeeForm (UI Component), TimecardForm (UI Component)	-
TimecardController	TimecardController (Controller for Timecard Process)	TimecardService (Handles business logic for Timecards)
EmployeeEntity	EmployeeEntity (Data Model for Employee)	EmployeeService (Handles business logic for Employee)
CreateEmployeeForm	CreateEmployeeForm (UI Component)	-
CreateEmployeeController	CreateEmployeeController (Controller for Employee Creation)	EmployeeService (Handles business logic for Employee Creation)
ProjectManagementDatabase	ProjectManagementDatabase (UI Component)	ProjectManagementService (Handles business logic for Project Management)
PurchaseOrder	MaintainPurchaseOrderForm (UI Component)	PurchaseOrderService (Handles business logic for Purchase Orders)
MaintainPurchaseOrderController	MaintainPurchaseOrderController (Controller for Purchase Order Management)	PurchaseOrderService (Handles business logic for Purchase Orders)
CreateAdministrativeReportForm	CreateAdministrativeReportForm (UI Component)	AdministrativeReportService (Handles business logic for generating reports)
CreateAdministrativeReportController	CreateAdministrativeReportController (Controller for Report Creation)	AdministrativeReportService (Handles report generation logic)
MaintainEmployeeInfoForm	MaintainEmployeeInfoForm (UI Component)	EmployeeService (Handles business logic for updating employee information)
MaintainEmployeeInfoController	MaintainEmployeeInfoController (Controller for Employee Information Maintenance)	EmployeeService (Handles business logic for updating employee information)
PayrollForm	PayrollForm (UI Component), PrinterForm (UI Component), BankSystemForm (UI Component)	PayrollService (Handles payroll processing logic)
PayrollController	PayrollController (Controller for Payroll Process)	PayrollService (Handles payroll business logic)
PrinterController	PrinterController (Controller for Printer Process)	-
BankSystemController	BankSystemController (Controller for Bank System Interaction)	BankTransactionService (Handles bank transaction processing)
Employee	EmployeeEntity (Data Model for Employee)	EmployeeService (Handles employee-related business logic)
Paycheck	PaycheckEntity (Data Model for Paycheck)	PaycheckService (Handles paycheck generation and processing)
