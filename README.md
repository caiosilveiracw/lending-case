# Loan Analysis

## Project Description

This project aims to analyze loan data to address key questions related to loan issuance, default rates, and profitability. The analyses are presented through various graphs that provide insights into the financial performance and trends within the dataset.

## Data Column Descriptions

### Clients Data

- **user_id**: Unique identifier for each user.
- **created_at**: Date and time when the user was created.
- **status**: Status of the user (approved, denied). Users with a status of "denied" cannot take new loans.
- **batch**: The batch to which the user belongs.
- **credit_limit**: The maximum amount the user can borrow.
- **interest_rate**: The annual interest rate assigned to the user.
- **denied_reason**: The reason for denying the user. This field is empty for approved users.
- **denied_at**: Date and time when the user was denied. This field is empty for approved users.

### Loans Data

- **user_id**: Unique identifier for each user.
- **loan_id**: Unique identifier for each loan.
- **created_at**: Date and time when the loan was created.
- **due_at**: Date and time when the loan is due.
- **paid_at**: Date and time when the loan was paid. This field is empty if the loan is not paid.
- **status**: Status of the loan (paid, default, ongoing). Ongoing loans are open, and a user cannot have two open loans at the same time. Defaulted loans mean the user cannot take new loans.
- **loan_amount**: The amount of the loan.
- **tax**: The tax on the loan (3.8% of the principal amount + 0.0082% of the principal amount per day for 90 days).
- **due_amount**: The total amount due on the loan (loan_amount + tax + 90 days of interest).
- **amount_paid**: The amount paid on the loan to date.

## Graph Components and Calculations

### Best Month for Issuing Loans

- **Columns Used**: `year_month`, `loan_id`, `loan_amount`.
- **Calculation**:
  - **Number of Loans**: Count of loans issued each month.
  - **Total Amount Borrowed**: Sum of loan amounts issued each month.
- **Graph**:
  - Bar chart showing the number of loans per month.
  - Line plot showing the total amount borrowed per month.

### Influence of Interest Rates on Default

- **Columns Used**: `interest_rate`, `status`, `loan_id`.
- **Calculation**:
  - **Default Rate**: Proportion of loans that defaulted for each interest rate.
- **Graph**:
  - Scatter plot showing the default rate against interest rates.

### Average Loan Amount by Interest Rate

- **Columns Used**: `interest_rate`, `loan_amount`.
- **Calculation**:
  - **Average Loan Amount**: Average loan amount for each interest rate.
- **Graph**:
  - Bar chart showing the average loan amount by interest rate.

### Average Loan Amount per Month

- **Columns Used**: `year_month`, `loan_amount`, `loan_id`.
- **Calculation**:
  - **Average Loan Amount**: Average loan amount per month.
- **Graph**:
  - Line plot showing the average loan amount per month.

### Average Loan Amount per Batch

- **Columns Used**: `batch`, `loan_amount`.
- **Calculation**:
  - **Average Loan Amount**: Average loan amount for each batch of clients.
- **Graph**:
  - Bar chart showing the average loan amount by batch.

### Customer Ranking (Top 10 Best and Worst)

- **Columns Used**: `user_id`, `loan_amount`, `amount_paid`, `status`.
- **Calculation**:
  - **Best Clients**: Top 10 clients ranked by the total amount paid.
  - **Worst Clients**: Top 10 clients ranked by the total default amount.
- **Graph**:
  - List of top 10 best and worst clients.

### Default Rate by Month and Batch

- **Columns Used**: `year_month`, `batch`, `loan_id`, `status`.
- **Calculation**:
  - **Default Rate**: Proportion of loans that defaulted for each month and batch.
- **Graph**:
  - Line plot showing the default rate by month.
  - Bar chart showing the default rate by batch.

### Operation Profitability Over Time

- **Columns Used**: `year_month`, `tax`, `loan_amount`, `interest_rate`, `status`.
- **Calculation**:
  - **Interest Revenue**: Sum of interest received each month.
  - **Default Losses**: Sum of default losses each month.
  - **Profit**: Difference between total interest received and total default losses each month.
- **Graph**:
  - Line plot showing the profit over time, formatted in millions.

## Usage Instructions

1. Clone the repository or download the files directly from GitHub.
2. Open the Jupyter Notebook `loan_analysis_case.ipynb` in a Jupyter environment.
3. Follow the cells in the notebook to see detailed analyses for each question.

## Repository Structure

- `loan_analysis_case.ipynb`: The main notebook containing the analyses.
- `README.md`: This file, with usage instructions.

## Contact
For questions or more information, contact via email at caio.silveira@cloudwalk.io.
