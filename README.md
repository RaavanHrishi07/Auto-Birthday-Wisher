# 🎂 Auto Birthday Wisher

A simple Python-based automation tool that checks birthdays stored in an Excel spreadsheet and automatically sends personalised birthday wishes through Gmail.

The application reads birthday information from an Excel file, compares each birthday with the current date, sends an email when a birthday matches, and records the year in which the person was wished to prevent duplicate wishes during the same year.

---

## ✨ Features

- 🎂 Automatically checks birthdays from an Excel spreadsheet
- 📧 Sends personalised birthday emails through Gmail
- 📝 Uses a custom message for each recipient
- 📅 Compares birthdays with the current date
- 🔄 Tracks the year in which a person was last wished
- 🛑 Prevents sending duplicate birthday wishes in the same year
- 📊 Automatically updates the Excel dataset
- 💻 Simple command-line interface
- 🖼️ Includes an example of a received birthday email

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| Python | Application development |
| Pandas | Reading and updating Excel data |
| OpenPyXL | Excel file handling |
| Datetime | Checking dates and current year |
| SMTP | Sending emails |
| Gmail SMTP | Email delivery |
| Excel | Storing birthday and recipient information |

---

## 📂 Project Structure

```text
Auto-Birthday-Wisher/
│
├── Auto B_Day Wisher.py
├── data.xlsx
├── emailReceived.jpg
├── README.md
└── .gitignore
```

### 📄 File Description

**`Auto B_Day Wisher.py`**

The main Python program that checks birthdays and sends birthday emails.

**`data.xlsx`**

The Excel spreadsheet containing recipient information such as names, birthdays, email addresses, personalised dialogues, and previously wished years.

**`emailReceived.jpg`**

Example screenshot showing a birthday email received after running the application.

**`README.md`**

Documentation and setup instructions for the project.

**`.gitignore`**

Prevents sensitive or unnecessary files from being uploaded to GitHub.

---

## 📊 Excel Dataset Format

The application expects the Excel file to contain the following columns:

| Column | Description |
|--------|-------------|
| Name | Name of the person |
| Birthday | Birthday of the person |
| Email | Recipient's email address |
| Dialogue | Personalised birthday message |
| LastWishedYear | Years in which the person has already been wished |

### Example

| Name | Birthday | Email | Dialogue | LastWishedYear |
|------|----------|-------|----------|----------------|
| Example User | 17-03-2000 | example@gmail.com | Happy Birthday! Have a wonderful day! | 2025 |

The Excel file should be named:

```text
data.xlsx
```

and should be placed in the same directory as the Python script.

---

## ⚙️ Requirements

Before running this project, make sure you have:

- Python 3.10 or later
- A Gmail account
- An internet connection
- Microsoft Excel or another Excel-compatible application
- Required Python packages

---

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/RaavanHrishi07/Auto-Birthday-Wisher.git
```

Navigate into the project directory:

```bash
cd Auto-Birthday-Wisher
```

---

### 2. Create a Virtual Environment

On Windows:

```bash
python -m venv venv
```

Activate the virtual environment:

```bash
.\venv\Scripts\activate
```

---

### 3. Install Required Packages

Install Pandas:

```bash
pip install pandas
```

Install OpenPyXL:

```bash
pip install openpyxl
```

Or install both together:

```bash
pip install pandas openpyxl
```

---

## 🔐 Gmail Configuration

The application uses Gmail's SMTP server to send birthday emails.

The program asks for the sender's Gmail address and authentication information at runtime.

```text
Enter your email:
Enter password for your email mentioned above:
```

### ⚠️ Security Notice

Never hard-code your Gmail password inside the Python source code.

Never upload passwords, API keys, access tokens, or other authentication credentials to GitHub.

For modern Gmail accounts, use Google's supported authentication and security methods rather than exposing your account password.

---

## ▶️ Running the Application

Make sure the virtual environment is activated and that `data.xlsx` is in the project directory.

Run:

```bash
python "Auto B_Day Wisher.py"
```

The application will ask for the sender's email:

```text
Enter your email:
```

Enter the Gmail address that will be used to send the birthday wishes.

The application will then request the required authentication information.

---

## 🔄 How the Application Works

The application follows these steps:

1. 📂 Reads the birthday dataset from `data.xlsx`.
2. 📅 Gets the current date.
3. 📆 Gets the current year.
4. 🔍 Checks each person's birthday from the Excel file.
5. 🎂 Compares the birthday with today's date.
6. 🔐 Checks whether the person has already been wished during the current year.
7. 📧 Sends a personalised birthday email when the conditions match.
8. 📝 Records the current year in `LastWishedYear`.
9. 💾 Saves the updated information back to `data.xlsx`.

---

## 📧 Email Format

The email subject used by the application is:

```text
Happy Birthday
```

The message body is taken from the recipient's `Dialogue` field in the Excel spreadsheet.

### Example

```text
Name1 Happy Birthday to you!!!
```

The recipient receives the message through Gmail.

---

## 🖼️ Example Output

The project includes an example screenshot:

```text
emailReceived.jpg
```

This image demonstrates what a successfully delivered birthday email can look like.

---

## 🛑 Duplicate Wish Prevention

The application keeps track of the year in which each person was wished.

Before sending an email, it checks:

```text
Today's date = Birthday
AND
Current year is not already recorded in LastWishedYear
```

If both conditions are satisfied, the birthday email is sent.

After sending the email, the current year is added to the `LastWishedYear` field.

This helps prevent the application from sending the same birthday wish multiple times during the same year.

---

## 📁 Data Update

After processing birthdays, the application saves the updated dataset back to:

```text
data.xlsx
```

The `LastWishedYear` information is updated for recipients whose birthday wishes were successfully processed.

---

## 🚨 Troubleshooting

### `ModuleNotFoundError: No module named 'pandas'`

Install Pandas:

```bash
pip install pandas
```

---

### `ModuleNotFoundError: No module named 'openpyxl'`

Install OpenPyXL:

```bash
pip install openpyxl
```

---

### `FileNotFoundError: data.xlsx`

Make sure:

```text
data.xlsx
```

is located in the same directory as:

```text
Auto B_Day Wisher.py
```

---

### Gmail Authentication Error

If Gmail rejects the login attempt, check your Google account security settings and use a supported authentication method.

Do not disable security protections or expose your Gmail password to make the application work.

---

### Birthday Email Is Not Sent

Check the following:

- The birthday date in `data.xlsx` is correct.
- The date format matches the format expected by the program.
- The recipient's email address is correct.
- `LastWishedYear` does not already contain the current year.
- The internet connection is working.
- Gmail authentication is configured correctly.

---

## 🔒 Security

This project handles email authentication information, so security should be taken seriously.

### Never upload:

```text
Passwords
API keys
Access tokens
Authentication credentials
Private configuration files
```

Use `.gitignore` to prevent sensitive files from being accidentally committed.

Never publish real passwords or personal authentication information in the source code or GitHub repository.

---

## 🚀 Future Improvements

Possible improvements for future versions include:

- 🖥️ Add a graphical user interface
- 🔐 Use modern OAuth-based Gmail authentication
- 📁 Allow users to select the Excel file
- 📧 Support multiple email providers
- 📝 Add HTML email templates
- 🎨 Add custom birthday email designs
- 📅 Support recurring automated execution
- ⏰ Add scheduled daily execution
- 📊 Add email delivery logs
- ❌ Improve error handling
- 🔔 Add notification when an email is successfully sent
- 📋 Add recipient management through a GUI
- ☁️ Add cloud-based scheduling

---

## 🎯 Project Purpose

The purpose of this project is to automate birthday wishes and reduce the need to manually remember and send birthday emails.

By maintaining birthday information in an Excel spreadsheet, the application can automatically identify birthdays and send personalised messages to the appropriate recipients.

The project also demonstrates practical usage of Python for:

- File handling
- Data processing
- Date comparison
- Email automation
- Spreadsheet management
- Basic workflow automation

---

## 👨‍💻 Author

**Hrishikesh Sharma**

GitHub:

**RaavanHrishi07**

---

## ⭐ Support

If you find this project useful or interesting, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is intended for educational and personal use.

You are free to study and modify the code for learning and personal projects.