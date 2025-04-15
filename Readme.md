:

📄 Employee Payslip Generator & Email Sender
This project is a Python-based application that reads employee salary data from an Excel spreadsheet, generates professional payslips in PDF format, and emails them to individual employees.

🚀 Features
Reads employee salary details from an Excel file

Generates detailed PDF payslips with:

Employee info (Name, ID, Department, Email, Date)

Salary breakdown (Basic, Allowance, Deductions, Net Salary)

Signature section for both employee and HR

Emails the generated payslips to each employee

Handles missing data (e.g., missing department)

🛠️ Prerequisites
Before running the script, ensure you have the following installed:

bash
Copy
Edit
pip install pandas reportlab openpyxl
Also, you must enable less secure apps or generate an App Password if you're using Gmail for the sender email.

📂 Folder Structure
bash
Copy
Edit
project_folder/
├── employee salary.xlsx        # Your Excel input file
├── employee_payslips/          # Auto-created folder for generated PDFs
├── script.py                   # Main Python script
└── README.md                   # Project README
🧾 Excel File Format
The Excel file should have the following columns:

Employee ID	Name	Email	Basic Salary	Allowance	Deductions	Department
Make sure the headers are spelled exactly as shown (case-sensitive).

🔐 Email Setup
Update the following configuration in the script:

python
Copy
Edit
sender_email = "your_email@example.com"
sender_password = "your_app_password"
If using Gmail:

Enable 2FA on your account

Go to your Google Account → Security → App passwords

Generate one and paste it as sender_password

🧾 Payslip Layout
Each PDF includes:

Company name: F.MOTORS

Title: EMPLOYEE PAYSLIP

Employee details: Name, ID, Email, Department, Date

Salary breakdown: Basic Salary, Allowance, Deductions, Net Salary

Signature boxes

Footer: Auto-generated notice

✉️ Email Contents
Each employee receives an email with the subject:

sql
Copy
Edit
F.MOTORS - Payslip for <Current Date>
Body:

pgsql
Copy
Edit
Dear <Employee Name>,

Here is your payslip for the month of <Current Date>.

Best regards,  
F.MOTORS
And the generated PDF is attached.

▶️ How to Run
Place your employee salary.xlsx in the same folder as the script.

Update the sender email and password.

Run the script:

bash
Copy
Edit
python script.py
You'll see logs showing PDF generation and email delivery status for each employee.

🛡️ Error Handling
If the Excel file is not found, an error is printed.

If any required columns are missing, you'll get a clear warning.

The last employee's department is auto-filled if missing.

📬 Sample Output
css
Copy
Edit
✅ Payslip generated for Jane Doe (EMP002)
📨 Email sent to jane.doe@example.com
