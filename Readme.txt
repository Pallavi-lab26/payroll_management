Payroll Management System
 Overview

The Payroll Management System is a Python-based application that automates employee salary processing. It integrates with Oracle Database and AWS S3 to fetch employee data, apply business rules, and calculate salaries including deductions.

The system also provides a GUI interface using Tkinter for easy interaction.

 Features
Fetch employee data from AWS S3 (CSV file)
Store processed data in Oracle Database
Apply global and designation-based salary rules
Calculate:
Gross Salary
Deductions (PF, Tax, Cess)
Net Salary
Prevent duplicate employee entries
User-friendly GUI using Tkinter
 Technologies Used
Python
Tkinter (GUI)
Oracle Database (oracledb)
AWS S3 (boto3)
CSV handling
 Project Structure
project/
│
├── payroll.py        # Backend logic
├── gui.py            # Tkinter GUI
├── Employee_details_1000.csv
└── README.md
 Setup Instructions
1. Install Dependencies
pip install oracledb boto3
2. Configure Oracle Database

Update your DB connection details in payroll.py:

user="your_username"
password="your_password"
dsn="your_dsn"
3. Configure AWS S3
Create an S3 bucket
Upload Employee_details_1000.csv
Set AWS credentials using environment variables:
export AWS_ACCESS_KEY=your_key
export AWS_SECRET_KEY=your_secret
4. Run the Application
Run CLI version:
python payroll.py
Run GUI version:
python gui.py
 Salary Calculation Logic
Gross Salary:
Basic Salary
HRA (% from DB)
DA (% from DB)
Special Allowance (% from DB)
Deductions:
PF (% from Global Rules)
Tax (% from Designation Rules)
Cess (% from Global Rules)
Net Salary:
Net = Gross - Total Deductions
 Database Tables
Employee_Master
emp_id
emp_name
designation
gross_salary
net_salary
Salary_Details
salary_id
basic_salary
hra
da
special_allowance
pf
cess
total_deductions
emp_id
Global_Rules
pf_pct
cess_pct
Designation_Rules
hra_pct
da_pct
special_pct
tax_pct
 Future Enhancements
Add login authentication
Export salary slips as PDF
Add employee search & update
Deploy as web application