# 1. Subsystem context diagrams
## a. Hệ thống con BankSystem:
  
## b. Hệ thống con PrintService:

## c. Hệ thống con ProjectManagementDatabase:

# 2. Analysis class to design element map
|  Analysis Class | Design Element |  
|-----------------|----------------|
| LoginForm | LoginForm|
| MaintainTimecardForm | MainEmployeeForm |
| TimecardController | TimecardController |
| PayrollController | PayrollController |
| PayCheck | PayCheck |
| BankService | BankService |
| SystemClockInterface | SystemCLockInterface |
| PayrollController | PayrollControllerImpl |
| Employee | EmployeeEntity |
| Timecard | TimecardEntity |
| Payroll | PayrollProcessor |
| BankTransaction | BankTransactionProcessor |
| PaymentUI | PaymentUIComponent |
| PrintService | PrintServiceProcessor |

# 3. Design element to owning package map
|  Design Element | "Owning" Package |  
|-----------------|----------------|
| LoginForm | Middleware::Security::GUIFramwork |
| MainEmployeeForm | Applications::Employee Activities |
| TimecardController | Applications::Employee Activities |
| SystemClockInterface | Applications::Payroll |
| PayrollController | Applications: Payroll |
| PayCheck | Business Services::Payroll Artifacts |
| BankService | Business::Banking |
| EmployeeEntity | Data Access::Employee Management |
| TimecardEntity | Data Access::Employee Management |
| PayrollProcessor | Business Services::Payroll Processing |
| BankTransactionProcessor | Business Services::Banking |
| PaymentUIComponent | Middleware::User Interface Components |
| PaymentUIComponent | Middleware::Print Services |


# 4. Architectural layers and their dependencies
  ![Diagram](https://www.planttext.com/api/plantuml/png/b591QiCm4Bph5IBtVA04azJqba8W-S0YBOwmh1MId69ANfP3dzGlL0uEbgocK1rtPdPs1dtVlhO-W0jzfva5qKA3VBMpLYi1GP7XUnZGhVWdu_493Txpjyvg6X2Fw2vAO8ASL8S2dAp914TQeql00mpZBC6kRFPyxRqo66dJrjmoQkipYlQvPObCVWT78kwbt6wpULTIQlm0XrMLc-sfQPHfoesxFfpHXAcQ4ZyEFc1NQnBjQBReYQ_NrJ88V-6zHy_AukxiHRW7ksZoiJhB-pSx3ncvcXhFoQAxXvjFIgylHAd1RFnFwg-rHWNCysVIfF4ei8ukIgBd8TxEs1QD7F_r3m000F__0m00)
