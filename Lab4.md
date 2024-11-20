| **Analysis Class**            | **Design Element (Application Layer)**                               | **Design Element (Business Services Layer)**                        |
|-------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| **LoginForm**                  | LoginForm                                            |                                                                  |
| **LoginController**            | LoginController              | UserService (Handles user authentication)                           |
| **TimecardForm**               | TimecardForm (UI Component)                                         |                                                                  |
| **TimecardController**         | TimecardController (Controller for Timecard Process)               | TimecardService (Handles timecard processing logic)                 |
| **PayrollForm**                | PayrollForm (UI Component)                                          |                                                                   |
| **PayrollController**          | PayrollController (Controller for Payroll Process)                 | PayrollService (Handles payroll processing logic)                    |
| **PrinterForm**                | PrinterForm (UI Component for Printing Paychecks)                   | -                                                                   |
| **PrinterController**          | PrinterController (Controller for Printing Paychecks)              | PrinterService (Handles printing logic for paychecks)                |
| **BankSystemForm**             | BankSystemForm (UI Component for Bank Transactions)                 | -                                                                   |
| **BankSystemController**       | BankSystemController (Controller for Bank Transactions)            | BankTransactionService (Handles bank transactions)                  |
| **EmployeeEntity**             | EmployeeEntity (Data Model for Employee Information)                | EmployeeService (Handles business logic related to Employee)        |
| **Paycheck**                   | Paycheck (Data Model for Paycheck)                                  | PaycheckService (Handles paycheck calculation and distribution)     |
| **CreateEmployeeForm**         | CreateEmployeeForm (UI Component for Creating Employee)             | -                                                                   |
| **CreateEmployeeController**   | CreateEmployeeController (Controller for Creating Employee)        | EmployeeService (Handles creation of new employees)                 |
| **SaveForm**                   | SaveForm (UI Component for Saving Employee Information)             | -                                                                   |
| **MaintainPurchaseOrderForm**  | MaintainPurchaseOrderForm (UI Component for Managing Purchase Orders) | -                                                                   |
| **MaintainPurchaseOrderController** | MaintainPurchaseOrderController (Controller for Managing Purchase Orders) | PurchaseOrderService (Handles Purchase Order Management) |
| **CreateAdministrativeReportForm** | CreateAdministrativeReportForm (UI Component for Creating Reports) | -                                                                   |
| **CreateAdministrativeReportController** | CreateAdministrativeReportController (Controller for Creating Reports) | AdministrativeReportService (Handles report generation)  |
| **MaintainEmployeeInfoForm**   | MaintainEmployeeInfoForm (UI Component for Employee Information Management) | -                                                               |
| **MaintainEmployeeInfoController** | MaintainEmployeeInfoController (Controller for Employee Information Management) | EmployeeService (Handles Employee Info Management) |
