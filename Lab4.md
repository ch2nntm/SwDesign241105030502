# Kết quả Lab 4:
## 1.Subsystem context diagrams
### 1.1 BankSystem:

![Diagram](https://www.planttext.com/api/plantuml/png/j991JiCm44NtFiMegoAHTb-XghImgCG2AISOt2bOSUp8urH4q9Enu4XS0JjAI9oiySRssF_Fcx5_lhvtxD7vkjI22sN0MIOXAfG5lX8ixgjAAubUMGDFs91Rm8U0CAH6PdZ6nbcj3zRuE9FhJkDOhrrjkWlBcpPy5TUHzxvcPIYuvEGkIXAd6PJnvCue2OvxD4NUiASoyJzHPLdv9OOiyera0HlebxTHRwCm1EDqD6VhohQI7cQeOqZGiO0gAqqb6S_Zz2d_G9NNBzokqlRy4tU0263ADt-gVZyH235_e2pR9WtTm8Do93rqL71HACONxZwpRDuWCMzPT4wC7zz9rfvwvv44Lglj03-9JulOaJd5__aB003__mC0)

### 1.2 PrintService:
![Diagram](https://www.planttext.com/api/plantuml/png/b58nJWCn4EpzYbMgK5pIHoWAe1H8515vWJ5BPCLdczqruWHv6GLFuWlOTnVf72gsiRqpdXcl_FFrlM7H9AbrYe_M0mL6fQ8sHtr0cDt4wApHOeE71zqXpU13GIxZD3FiT4V1kRlWfQn88rfgkQJaHyBygc-Vr6cYVPlOUimgUwGtQv1h1-i5wKKRXFiTvSF8gXnY0UPnC7d464XW1SFcR3b9EvMnRNJOeXUkzQk8rOrzUkAE1TkB6VIS7lXtjkoL4rZfnhvIVoVQDEkB2HILruGiq7jOVr0ruVgpQQhNgWekYjFKAzY-eqc2WvwQOel5-fnjW_uv_vDV0000__y30000)

### 1.3 ProjectManagementDatabase:
![Diagram](https://www.planttext.com/api/plantuml/png/h5BDJiCm3BxdAQoTjaEtUuMc0HFI990c-WHUPafOcfROHQfWJyQ1H-8LIBOUMgPmmfT4zlTZE_d-_5gne9UsieeFne6lcPHgK1-m99XSDuqr6iNK3kwn8p-1TmKXj4Lcs6BdQsjlQoVn9DzNOomMldKzO3exfO_gED2-QTau2Ye5-JUZYSSEnWdv9zG4cwslNqZB0xf0hCX9pnYvbIGzRes2KweQMtT4cpNaK8Wthfo5sm3IjpIO9cLZWjOfmUbUHgDTWABV3fcWQ7VSiL3rQv59md-C65eBaaQwKKrTlbwMBV_OTWwFzDeI2pHd2EoZJffmzP5boQsg92rsaLv83dSa-ldidORDvylHj2jo-_ZBVm000F__0m00)


## 2.Analysis class to design element map:
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


## 3.Design element to owning package map
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



## 4. Architectural layers and their dependencies
![Diagram](https://www.planttext.com/api/plantuml/png/X9H1JiCm44NtSugHDwnwWoggX6350i49J1aLguudiWqeGfoC1KVY2ZID6yTnNEzV_d_A7_dlvtVdlBJ-lTNWZigWPKS0dTmVvO7mWG_AtBDjSRlLiYVRD8XVy1s9HzbRrdgDkI1tRQUv9xh6F577rbzjEhlSil537zbIKX2gWnUjEZdAbRaiyfdiXzfJHR52ZQq5AAiSQASysxxIMWV7uZ87S7DYjFIAZNjJdSCNyfz41i-O0p6TZS3Dfa6nc4uWYDdT12WRJe2Odqx0yjc6k7W_0LjkTe8WzqWImwyMiAAIA4PmJQQGcGlDF2SCiY_JlBXAr4p9REQfE-MMAmlOaNaTte5_0000__y30000)
