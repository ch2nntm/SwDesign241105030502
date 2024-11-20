| **Analysis Class**            | **Design Element (Application Layer)**   | **Design Element (Business Services Layer)**    |
|-------------------------------|------------------------------------------|-------------------------------------------------|
| **LoginForm**                 | LoginForm                                |                                                 |
| **LoginController**           | LoginController                          | UserService                                     |
| **TimecardForm**              | TimecardForm                             |                                                 |
| **TimecardController**        | TimecardController                       | TimecardService                                 |
| **PayrollForm**               | PayrollForm                              |                                                 |
| **PayrollController**         | PayrollController                        | PayrollService                                  |
| **PrinterForm**               | PrinterForm                              |                                                 |
| **PrinterController**         | PrinterController                        | PrinterService                                  |
| **BankSystemForm**            | BankSystemForm                           |                                                 |
| **BankSystemController**      | BankSystemController                     | BankTransactionService                          |
| **EmployeeEntity**            | EmployeeEntity                           | EmployeeService                                 |
| **Paycheck**                  | Paycheck                                 | PaycheckService                                 |
| **CreateEmployeeForm**        | CreateEmployeeForm                       |                                                 |
| **CreateEmployeeController**  | CreateEmployeeController                 | EmployeeService                                 |
| **SaveForm**                  | SaveForm                                 |                                                 |
| **MaintainPurchaseOrderForm** | MaintainPurchaseOrderForm                |                                                 |
| **MaintainPurchaseOrderController** | MaintainPurchaseOrderController    | PurchaseOrderService                            |
| **CreateAdministrativeReportForm** | CreateAdministrativeReportForm      |                                                 |
| **CreateAdministrativeReportController** | CreateAdministrativeReportController  | AdministrativeReportService             |
| **MaintainEmployeeInfoForm**   | MaintainEmployeeInfoForm  |                                                               |
| **MaintainEmployeeInfoController** | MaintainEmployeeInfoController      | EmployeeService                                 |






| **Design Element**             | **Owning Package**             |
|--------------------------------|--------------------------------|
| **LoginForm**                  | ui::login                      |
| **PayrollForm**                | ui::payroll                    |
| **EmployeeForm**               | ui::employee                   |
| **ReportForm**                 | ui::report                     |
| **LoginController**            | application::login             |
| **PayrollController**          | application::payroll           |
| **EmployeeController**         | application::employee          |
| **ReportController**           | application::report            |
| **EmployeeService**            | business services::employee    |
| **PayrollService**             | business services::payroll     |
| **ReportService**              | business services::report      |
| **SecurityFilter**             | middleware::security           |
| **AuthenticationManager**      | middleware::security           |
