🏦 Console Bank Management System (Python + MySQL • CLI Application)

A fully functional console-based banking system built using Python, MySQL, and Colorama. It simulates essential banking operations such as opening an account, transferring money, checking balance, updating personal details, and deleting an account. All operations are fully secure with password verification and real database integration.

✨ Features ✔ 1. Open a New Account

Enter your name, mobile number, and initial deposit

Auto–generated unique ATM/Account Number

Password confirmation for security

Stores user data in MySQL database

✔ 2. Transfer Money

Validates sender & receiver accounts

Prevents transfer if balance is insufficient

Password authentication required

Updates both accounts’ balances in database

✔ 3. Check Balance

Secure login using password

Retrieves the latest balance from database

Displays amount in a clean console interface

✔ 4. Update User Details

You can update:

Name

Phone Number

Password You can also modify multiple details in one session.

✔ 5. Delete Account

Password security check

Removes your entire record from MySQL

🔧 Tech Stack Component Technology Language Python Database MySQL CLI Styling Colorama Platform Windows CMD / Terminal 📂 Recommended Project Structure Console_Bank_management_system/ │── main.py │── README.md └── requirements.txt

🗄️ MySQL Database Setup

Run this SQL before running the program:

CREATE DATABASE bank;

USE bank;

CREATE TABLE customer ( name VARCHAR(50), atmno VARCHAR(50) PRIMARY KEY, totalamount FLOAT, pass INT, phoneno BIGINT );

📦 Installation & Setup Guide

Install Required Python Modules
pip install mysql-connector-python colorama

Update MySQL Credentials in Code
mydb = myconn.connect( host="localhost", user="root", password="YOUR_PASSWORD", database="bank" )

Run the Application
python main.py

🖥️ Flow Diagram (How It Works) ┌───────────────────────────┐ │ Console Bank System │ └──────────────┬─────────────┘ │ ┌──────────┴───────────┐ │ Main Menu │ └──────────┬───────────┘ │ ┌────────┬─────┼────────┬─────────┬─────────┐ │ Open │Trans│ Check │ Update │ Delete │ │Account │Money│ Balance │ Details │ Account │ └────────┴─────┴────────┴─────────┴─────────┘

📝 Example Outputs ✔ Account Created Your account no is: 12345 Your password is: 4321

✔ Money Transfer Amount transfer successful! Now your amount is: 4700.0

✔ Wrong Password You entered wrong password... 2 tries available.

🔐 Security Notes

Passwords are stored as integers (can be improved to hashing)

Sensitive operations require password:

Money transfer

Checking balance

Updating details

Deleting account

Input validation and multi-step authentication for safety

🚀 Planned Future Upgrades

🔒 Password hashing & stronger security

💵 Add deposit/withdrawal

📜 Add transaction history

👨‍💼 Add admin dashboard

🖥 GUI version using Tkinter or PyQt

🌐 Convert to Web App using Flask/Django

🤝 Contribution

Pull requests are welcome! Feel free to suggest improvements or open issues.

⭐ Author

Nitin Sheoran
