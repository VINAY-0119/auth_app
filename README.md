# Flask User Authentication System

A simple yet secure user authentication system built with Python (Flask), HTML, CSS, and SQLite.  
This project demonstrates a clear login workflow with server-side validation and a minimal, user-friendly interface.

---

## Features

- Username and password authentication  
- Flask backend with clean, efficient routing  
- Lightweight SQLite database for user storage  
- Responsive and accessible login page  
- Real-time feedback with flash messages  
- Modular and maintainable codebase  

---

## Technology Stack

- **Backend:** Python 3.x, Flask  
- **Frontend:** HTML5, CSS3  
- **Database:** SQLite  
- **Tools:** Git, VS Code (recommended)  

---

## Project Structure

flask_user_auth/
│
├── app.py # Flask app source code
├── users.db # SQLite database file
│
├── templates/ # HTML templates
│ └── login.html
│
└── static/ # Static files
└── style.css

yaml
Copy code

---

## Prerequisites

- Python 3.6 or newer  
- Pip package manager  
- Basic command line knowledge  

---

## Setup Instructions

1. **Clone the repository**

```bash
git clone https://github.com/your-username/flask_user_auth.git
cd flask_user_auth
Install dependencies

bash
Copy code
pip install flask
Initialize the database

Create a file called init_db.py with this content:

python
Copy code
import sqlite3

conn = sqlite3.connect("users.db")
cursor = conn.cursor()

cursor.execute("""
CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username TEXT NOT NULL UNIQUE,
    password TEXT NOT NULL
)
""")

cursor.execute(
    "INSERT OR IGNORE INTO users (username, password) VALUES (?, ?)",
    ("admin", "1234")
)

conn.commit()
conn.close()
Run the script:

bash
Copy code
python init_db.py
Run the Flask app

bash
Copy code
python app.py
Open your browser at:

cpp
Copy code
http://127.0.0.1:5000
Usage
Log in with the default user:

Username: admin

Password: 1234

A successful login shows a personalized welcome message.

Incorrect login attempts display error messages.

Security Notice
This project is for educational use only. Storing passwords in plaintext is unsafe and not recommended for production. For production systems, you should:

Use password hashing (werkzeug.security.generate_password_hash)

Employ secure session management

Use environment variables for sensitive config

Deploy over HTTPS

Future Improvements
User registration and password recovery

Password hashing and salting

Session expiration and logout

Role-based access control

UI improvements with modern frameworks

Automated testing and input validation
