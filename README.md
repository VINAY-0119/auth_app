# Flask User Authentication System

A robust and clean user authentication system built using Python (Flask), HTML, CSS, and SQLite.  
Designed to showcase a secure login flow with server-side validation and a minimalistic, user-friendly interface.

---

## Key Features

- Secure user login via username and password  
- Backend powered by Flask with efficient routing  
- Lightweight SQLite database for user management  
- Responsive, clean, and accessible login UI  
- Clear feedback with flash messaging for authentication errors  
- Modular codebase designed for easy maintenance and extension  

---

## Technology Stack

- **Backend:** Python 3.x, Flask  
- **Frontend:** HTML5, CSS3  
- **Database:** SQLite  
- **Development Tools:** Git, VS Code (recommended)  

---

## Project Structure

flask_user_auth/
│
├── app.py # Flask application source code
├── users.db # SQLite database file
│
├── templates/ # HTML templates
│ └── login.html
│
└── static/ # Static assets (CSS files)
└── style.css

yaml
Copy code

---

## Prerequisites

- Python 3.6 or higher installed  
- Pip package manager  
- Basic familiarity with terminal/command line  

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/your-username/flask_user_auth.git
cd flask_user_auth
2. Install dependencies
bash
Copy code
pip install flask
3. Initialize the database
Run the following script once to create the users table and insert a default user:

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
You can run this in a Python shell or save it as a script and execute it.

4. Run the Flask application
bash
Copy code
python app.py
By default, the app will start on:

cpp
Copy code
http://127.0.0.1:5000
Open this URL in your browser to access the login page.

Usage
Use the default credentials to log in:

Username: admin

Password: 1234

On successful login, a personalized welcome message appears.

Invalid credentials display an error message.

Security Considerations
This project is intended for educational and demonstration purposes. Plaintext password storage is insecure and should never be used in production. For production readiness:

Implement password hashing (e.g., werkzeug.security.generate_password_hash)

Use secure session management and cookies

Manage configuration and secrets via environment variables

Deploy using HTTPS to encrypt traffic

Roadmap for Improvements
Implement user registration and password reset

Add secure password hashing and salting

Build logout and session expiration functionality

Introduce role-based access controls

Enhance UI/UX with modern frameworks

Write comprehensive tests and validation

License
This repository is open source and free for educational use.
