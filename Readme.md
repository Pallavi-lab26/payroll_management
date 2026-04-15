# **Payroll Management System**



* **Overview**

&#x20;  The Payroll Management System is a Python-based application that automates employee salary processing. It integrates with Oracle Database and AWS S3 to fetch employee data, apply                 business rules, and calculate salaries including deductions.

The system also provides a GUI interface using Tkinter for easy interaction.



* **Features**

&#x20;  Fetch employee data from AWS S3 (CSV file)

&#x20;  Store processed data in Oracle Database

&#x20;  Apply global and designation-based salary rules



* **Calculate:**

&#x20;  Gross Salary

&#x20;  Deductions (PF, Tax, Cess)

&#x20;  Net Salary

&#x20;  Prevent duplicate employee entries

&#x20;  User-friendly GUI using Tkinter



* **Technologies Used**

&#x20;  Python

&#x20;  Tkinter (GUI)

&#x20;  Oracle Database (oracledb)

&#x20;  AWS S3 (boto3)

&#x20;  CSV handling



* **Project Structure**

project/

│

├── payroll.py        # Backend logic

├── gui.py            # Tkinter GUI

├── Employee\_details\_1000.csv

└── README.md



* &#x20;**Setup Instructions**

&#x20;   1. Install Dependencies

&#x20;   pip install oracledb boto3

&#x20;   2. Configure Oracle Database



* **Update your DB connection details in payroll.py:**

user="your\_username"

password="your\_password"

dsn="your\_dsn"

3\. Configure AWS S3

Create an S3 bucket

Upload Employee\_details\_1000.csv

Set AWS credentials using environment variables:

export AWS\_ACCESS\_KEY=your\_key

export AWS\_SECRET\_KEY=your\_secret

4\. Run the Application

Run CLI version:

python payroll.py

Run GUI version:

python gui.py



* **Salary Calculation Logic**

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



* **Database Tables**

&#x20;  Employee\_Master

&#x20;  emp\_id

&#x20;  emp\_name

&#x20;  designation

&#x20;  gross\_salary

&#x20;  net\_salary



* **Salary\_Details**

&#x20;  salary\_id

&#x20;  basic\_salary

&#x20;  hra

&#x20;  da

&#x20;  special\_allowance

&#x20;  pf

&#x20;  cess

&#x20;  total\_deductions

&#x20;  emp\_id



* **Global\_Rules**

&#x20;   pf\_pct

&#x20;   cess\_pct



* **Designation\_Rules**

&#x20;  hra\_pct

&#x20;  da\_pct

&#x20;  special\_pct

&#x20;  tax\_pct



* **Future Enhancements**

&#x20;  Add login authentication

&#x20;  Export salary slips as PDF

&#x20;  Add employee search \& update

&#x20;  Deploy as web application

