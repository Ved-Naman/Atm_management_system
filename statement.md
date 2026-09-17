# Problem Statement: Automated Teller & Bank Management System (BMS)

## 1. Problem Statement
Traditional retail banking counters and manual record systems suffer from long queue times, high clerical overhead, and restricted operating hours. Customers seeking routine services—such as cash deposits, cash withdrawals, PIN changes, balance inquiries, and mini statement generation—face operational friction. Furthermore, manual bookkeeping is prone to accounting mismatches and lacks automated transaction audit trails.

There is a direct need for an interactive, graphical ATM and Bank Management application that simulates automated self-service banking. The system must authenticate customers, manage multi-step customer onboarding, ensure accurate balance calculations, and persist all financial operations in a relational database.

## 2. Scope of the Project
The Bank Management System is a desktop-based Java Swing & JDBC application that automates core retail banking and ATM operations:
- Multi-step customer registration capturing personal, demographic, and account configuration details across a 3-tier onboarding form (`Signup`, `Signup2`, `Signup3`).
- Secure card and PIN-based user authentication (`Login`).
- Core transactional modules: Cash Deposit (`Deposit`), Cash Withdrawal (`Withdrawl`), and Preset Quick Cash Dispensation (`FastCash`).
- Account self-service operations: Balance Inquiry (`BalanceEnquriy`), PIN Modification (`Pin`), and Recent Activity Tracking (`mini`).
- Relational data persistence using MySQL connected through Java Database Connectivity (`Connn`).

*Out of Scope:* Physical hardware integration (hardware card reader, currency counting mechanisms) and remote banking protocols (inter-bank network switches).

## 3. Target Users
- **Bank Customers:** Account holders performing balance checks, withdrawals, deposits, fast cash operations, mini-statement reviews, and PIN modifications via an ATM interface.
- **Branch Administrators / Onboarding Staff:** Bank staff overseeing the multi-stage customer onboarding process and account creation.

## 4. High-Level Features
- **Multi-Stage Onboarding:** Progressive profile creation across three structured forms collecting identity, financial status, and initial service preferences.
- **Card & PIN Authentication:** Card-number and four-digit PIN verification before granting access to the main ATM transaction dashboard.
- **Interactive ATM Dashboard (`main_Class`):** Central menu facilitating single-click navigation to financial services.
- **Preset & Custom Cash Dispensation:** Fast cash shortcuts (100, 500, 1000, etc.) and custom withdrawal routines with instant balance validation.
- **Audit & Mini Statement:** Tabular display of recent debits and credits linked to the authenticated card number.