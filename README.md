# Bank Management & ATM System

## Overview of the Project
The Bank Management System is a comprehensive desktop application built with Java Swing and JDBC. It simulates real-world ATM and retail banking operations, allowing users to securely create accounts, authenticate via card and PIN, and perform daily financial transactions. All data, including customer profiles and transaction histories, is persistently managed in a MySQL relational database.

## Features
* **Multi-Tier Customer Onboarding:** A three-step registration process capturing personal details (`Signup`), demographic information (`Signup2`), and account configuration (`Signup3`).
* **Secure Access:** Card number and PIN-based authentication (`Login`) granting access to the primary ATM dashboard (`main_Class`).
* **Core Banking Transactions:** Real-time processing for depositing funds (`Deposit`) and withdrawing cash (`Withdrawl`) with automated balance validation.
* **Quick Services:** Pre-set cash withdrawal limits for faster transactions (`FastCash`).
* **Account Tracking:** Instant balance calculation (`BalanceEnquriy`) and transaction history tracking (`mini` statement).
* **Security Management:** Secure module for users to update their account PIN (`Pin`).

## Technologies/Tools Used
* **Programming Language:** Java (JDK 8 or higher)
* **GUI Framework:** Java Swing & AWT
* **Database:** MySQL
* **Database Connectivity:** JDBC (MySQL Connector/J)
* **IDE:** IntelliJ IDEA

## Steps to Install & Run the Project
1. **Clone or Download:** Extract the `Bank_management` folder to your local machine.
2. **Database Setup:** Open your MySQL client and create a database (e.g., `bankSystem`). Execute your SQL scripts to build the required tables (`signup`, `signuptwo`, `signupthree`, `login`, and `bank`).
3. **Configure Credentials:** Open `src/code/Connn.java` in IntelliJ IDEA. Update the JDBC connection string with your local MySQL username (typically `root`) and password.
4. **Open in IDE:** Launch IntelliJ IDEA, select **Open**, and choose the `Bank_management` directory.
5. **Add Dependencies:** Navigate to **File > Project Structure > Modules > Dependencies**. Click the `+` icon, select **JARs or Directories**, and add the `mysql-connector-java.jar` file to your External Libraries.
6. **Execute:** Right-click on `Signup.java` (for a new user) or `Login.java` (for an existing user) in the project explorer and select **Run** to launch the GUI.

## Instructions for Testing
1. **Onboarding Test:** Run `Signup.java`. Fill out all fields across the three forms. Verify that the final submission generates a Card Number and PIN. Open your MySQL client and run `SELECT * FROM signupthree;` to confirm the data was inserted successfully.
2. **Authentication Test:** Run `Login.java`. Intentionally input an incorrect PIN to verify the error handling (a Swing dialog should appear). Then, log in with the correct credentials generated during the onboarding test to ensure it successfully routes to `main_Class`.
3. **Transaction Test:** From the main dashboard, click **Deposit**, enter `5000`, and confirm. Next, click **Withdrawl** and attempt to withdraw `10000`. The system must block this transaction and show an "Insufficient Balance" warning. Withdraw `2000` successfully.
4. **Audit Test:** Navigate back to the dashboard. Click **Mini Statement** and **Balance Enquiry** to confirm the system accurately reflects the $3000 remaining balance and lists both the initial deposit and the subsequent withdrawal.
## Project Structure
```text
Bank_management/
├── .idea/
├── icon/                              # Graphical assets and ATM interface background images
├── src/
│   └── code/
│       ├── Connn.java                 # JDBC connection manager
│       ├── Login.java                 # Card and PIN login interface
│       ├── Signup.java                # Customer onboarding - Step 1: Personal details
│       ├── Signup2.java               # Customer onboarding - Step 2: Additional details
│       ├── Signup3.java               # Customer onboarding - Step 3: Account & card config
│       ├── main_Class.java            # Main ATM dashboard menu
│       ├── Deposit.java               # Cash deposit window
│       ├── Withdrawl.java             # Cash withdrawal window
│       ├── FastCash.java              # Quick cash withdrawal options
│       ├── BalanceEnquriy.java        # Balance inquiry screen
│       ├── Pin.java                   # PIN change utility
│       └── mini.java                  # Mini statement display
├── statement.md                       # Project scope and problem statement
└── README.md                          # Project documentation