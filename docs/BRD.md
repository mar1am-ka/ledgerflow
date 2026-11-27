# LedgerFlow
## Business Requirements Document

Status: Draft
Version: 1.0

---

## 1. Project Overview

### 1.1 Project Description

LedgerFlow is a personal finance management and analytics platform designed to help individuals manage their financial activities.

The platform enables users to manage multiple financial accounts, record income and expenses, perform internal transfers, organize transactions into categories, and monitor their financial status through interactive dashboards and analytical reports.

LedgerFlow aims to provide users with a centralized environment for tracking their finances, understanding their spending habits, and making more informed financial decisions.

### 1.2 Target Audience

The primary target audience consists of individuals who want to organize, monitor, and analyze their personal finances.

### 1.3 Project Goals

- Provide centralized financial account management.
- Simplify income and expense tracking.
- Enable users to monitor their spending habits.
- Provide meaningful financial insights through analytics.
- Improve financial organization and awareness.
- Maintain accurate and consistent financial records.
count synchronization

##2. Problem Statement

Managing personal finances can become difficult when individuals use multiple accounts, manually track transactions, and lack a centralized view of their financial activities.

Without proper financial organization, users may struggle to monitor expenses, control spending, establish budgets, and understand their overall financial position.

LedgerFlow aims to address these challenges by providing a centralized platform for managing and analyzing personal finances.

##3. Project Scope

###3.1 In Scope

The initial version will include:

User registration and authentication.

Financial account management.

Income and expense management.

Internal account transfers.

Transaction categorization.

Double-entry bookkeeping.

Budget management.

Financial analytics and dashboards.

Financial reports.

Currency exchange rate integration.

Notifications.

Audit logging.

###3.2 Out of Scope

The initial version will not include:

Direct bank account connections.

Actual money transfers through banking networks.

Payment processing.

Loan management.

Stock trading or investment execution.

Users will manually manage their financial accounts and record their transactions.

##4. User Roles

###4.1 Registered User

The primary user of LedgerFlow.

A registered user can:

Manage their personal profile.

Create and manage financial accounts.

Record income and expenses.

Transfer funds between their accounts.

Manage transaction categories.

Create and monitor budgets.

View financial analytics and reports.

Manage notification preferences.

###4.2 Guest

An unauthenticated visitor who can:

Access the registration page.

Access the login page.

View publicly available information about the platform.

##5. Functional Requirements

###5.1 Identity and User Management

The system shall allow users to register using their personal information.

The system shall authenticate users using their credentials.

The system shall allow users to log out.

The system shall allow users to update their profiles.

The system shall prevent unauthorized access to personal financial information.

The system shall support password recovery.

5.2 Account Management

Users shall be able to create multiple financial accounts.

Users shall be able to specify account names, types, and currencies.

Users shall be able to view account balances.

Users shall be able to update account information.

Users shall be able to archive accounts.

Users shall be able to view the transaction history of individual accounts.

Supported account types may include:

Cash.

Checking accounts.

Savings accounts.

Other manually managed financial accounts.

###5.3 Transaction Management

Users shall be able to record income transactions.

Users shall be able to record expense transactions.

Users shall be able to select the account associated with each transaction.

Users shall be able to assign categories to transactions.

Users shall be able to add transaction descriptions and dates.

Users shall be able to view transaction history.

Users shall be able to search and filter transactions.

Users shall be able to edit or delete eligible transactions while preserving financial record consistency.

5.4 Transfer Management

Users shall be able to transfer money between their own accounts.

Users shall specify the source account, destination account, and transfer amount.

The system shall update the affected account balances consistently.

The system shall record both sides of a transfer.

Users shall be able to view their transfer history.

###5.5 Category Management

Users shall be able to organize transactions into categories.

The system shall provide predefined categories.

Users shall be able to create custom categories.

Users shall be able to edit and archive custom categories.

Categories shall support both income and expense classification.

###5.6 Budget Management

Users shall be able to create budgets for specific spending categories.

Users shall specify budget amounts and time periods.

The system shall calculate spending against the allocated budget.

The system shall display remaining budget amounts.

The system shall notify users when spending approaches or exceeds their budgets.

###5.7 Ledger Management

The system shall maintain financial records using double-entry bookkeeping.

Each posted financial transaction shall generate corresponding debit and credit entries.

The total debit amount shall equal the total credit amount for each journal entry.

Posted financial records shall preserve their audit history.

Corrections to posted transactions shall maintain the integrity of previous financial records.

###5.8 Analytics and Dashboard

The system shall provide users with an overview of their financial activities.

Users shall be able to view:

Total income.

Total expenses.

Net financial position.

Spending distribution by category.

Monthly income and expense comparisons.

Budget utilization.

Financial trends over selected periods.

###5.9 Reports

Users shall be able to generate financial summaries.

Users shall be able to filter reports by date range.

Users shall be able to view income and expense reports.

Users shall be able to view account activity reports.

Users shall be able to export reports in supported formats.

###5.10 Currency Management

Accounts shall support different currencies.

The system shall retrieve exchange rate information from an external provider.

Users shall be able to view converted financial summaries.

Historical transactions shall preserve their original transaction currency and amount.

Exchange rate information shall include its retrieval date and source.

###5.11 Notifications

The system shall:

Notify users when budget thresholds are reached.

Notify users about relevant account activities.

Support configurable notification preferences.

Provide notifications through supported channels.

###5.12 Audit Logging

The system shall maintain records of important financial activities and changes.

Audit records shall include:

The user responsible for the action.

The action performed.

The affected record.

The date and time of the action.

##6. Non-Functional Requirements

###6.1 Security

Passwords must be stored securely using appropriate password hashing.

Authentication and authorization must protect private user information.

Sensitive information must not be exposed through API responses or logs.

Communication must use HTTPS.

Users must only access their own financial records.

###6.2 Performance

The system should respond to normal requests within an acceptable response time.

Database queries should be optimized.

Analytics calculations should remain efficient as transaction records increase.

###6.3 Reliability and Data Integrity

Financial operations must maintain consistent account balances.

Related financial updates must be performed atomically.

Failed financial operations must not leave partially updated records.

Financial records must be protected against accidental inconsistencies.

###6.4 Maintainability

The application should follow a modular architecture.

Business logic should be separated from data access and presentation logic.

The system should support automated testing.

The codebase should be organized and documented.

###6.5 Scalability

The application should support increasing numbers of users and transactions.

Its architecture should allow future integration of additional services.

###6.6 Usability

The interface should be intuitive and responsive.

Financial information should be presented clearly.

Users should be able to navigate between accounts, transactions, budgets, and reports easily.

##7. Business Rules

###7.1 User Rules

Each registered user must have a unique email address.

Users must be authenticated before accessing personal financial information.

Users cannot access another user's financial accounts or transactions.

###7.2 Account Rules

Each account must belong to one user.

Every account must have a defined currency.

Account balances must be calculated consistently from their financial activity.

Accounts with historical financial activity should be archived rather than permanently deleted.

###7.3 Transaction Rules

Transaction amounts must be greater than zero.

Each transaction must belong to an account owned by the authenticated user.

Income increases the account balance.

Expenses decrease the account balance.

Every posted transaction must have corresponding balanced ledger entries.

###7.4 Transfer Rules

Source and destination accounts must be different.

Both accounts must belong to the same user.

Transfer amounts must be greater than zero.

The source account must have sufficient available funds.

Both sides of the transfer must be processed atomically.

Transfers involving different currencies must use a recorded exchange rate.

###7.5 Budget Rules

Budget amounts must be greater than zero.

Budgets must have valid starting and ending dates.

Spending calculations must consider the transactions assigned to the relevant category and period.

###7.6 Ledger Rules

Total debits must equal total credits for each journal entry.

Posted entries must not be silently overwritten.

Corrections must preserve the original financial history.

##8. Use Cases

Use Case

Description

Register

Create a new account

Login

Authenticate a user

Create Account

Add a financial account

Record Income

Record incoming money

Record Expense

Record outgoing money

Transfer Funds

Move funds between accounts

Manage Categories

Organize financial activities

Create Budget

Establish spending limits

View Dashboard

Monitor financial position

Generate Report

Review financial summaries

View Analytics

Analyze financial trends

Manage Profile

Update personal information

9. External Integrations

The system may integrate with:

Integration

Purpose

Exchange Rate API

Retrieve currency exchange rates

Email Provider

Send verification and notification emails

Future Financial Data Provider

Support optional bank account synchronization

External providers will be selected during technical design.

##10. Assumptions and Constraints

Assumptions

Users manually create and manage their financial accounts.

Users are responsible for recording their financial transactions.

The platform does not directly hold or transfer real money.

External exchange rate providers supply currency conversion information.

Each user manages their own financial information.

Constraints

The initial application will be developed as a web application.

The system will use a relational database.

Financial operations must preserve data integrity.

External integrations depend on provider availability.

##11. Acceptance Criteria

The initial version will be considered functionally complete when:

Users can register, log in, and securely manage their profiles.

Users can create and manage multiple financial accounts.

Users can record income and expenses.

Users can transfer funds between their accounts.

Account balances remain consistent after financial operations.

Financial transactions generate balanced ledger entries.

Users can categorize transactions and create budgets.

Users can view financial dashboards and reports.

Currency conversion information can be retrieved from an external provider.

Unauthorized users cannot access another user's financial information.

Important financial activities are recorded in audit logs.

Core business rules are covered by automated tests.

## Methods for each Entity
## 1.User

RegisterAsync() --> checks whether the email exists, the password is hashed, and saves a new user
LoginAsync() --> finds the user by email and verifies the password
updateUserAsync() --> update profile's First and last names
