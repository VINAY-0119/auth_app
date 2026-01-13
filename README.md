cat > README.md << 'EOF'
# Flask User Authentication System

A clean and simple user authentication system built with Python (Flask), HTML, CSS, and SQLite. Designed to demonstrate a basic login flow with server-side validation and a user-friendly interface.

---

## Features

- User login with username and password  
- Flask-powered backend with route handling  
- SQLite database for lightweight user data storage  
- Responsive and minimalistic login page  
- Flash messages to handle invalid login attempts  
- Modular and easy-to-extend project structure  

---

## Technology Stack

- **Backend:** Python, Flask  
- **Frontend:** HTML, CSS  
- **Database:** SQLite  

---

## Project Structure

\`\`\`
flask_user_auth/
│
├── app.py               # Flask application logic
├── users.db             # SQLite user database
│
├── templates/           # HTML templates
│   └── login.html
│
└── static/              # CSS stylesheets and static assets
    └── style.css
\`\`\`

---

## Setup and Installation

### Prerequisites

- Python 3.x installed  
- \`pip\` package manager available  

### Steps

1. **Clone the repository**

   \`\`\`bash
   git clone https://github.com/your-username/flask_user_auth.git
   cd flask_user_auth
   \`\`\`

2. **Install dependencies**

   \`\`\`bash
   pip install flask
   \`\`\`

3. **Initialize the database**

   Run the following Python script once to create the SQLite database and add a test user:

   \`\`\`python
   import sqlite3

   conn = sqlite3.connect("users.db")
   cursor = conn.cursor()

   cursor.execute("""
   CREATE TABLE IF NOT EXISTS users (
       id INTEGER PRIMARY KEY,
       username TEXT,
       password TEXT
   )
   """)

   cursor.execute(
       "INSERT INTO users (username, password) VALUES (?, ?)",
       ("admin", "1234")
   )

   conn.commit()
   conn.close()
   \`\`\`

4. **Start the Flask app**

   \`\`\`bash
   python app.py
   \`\`\`

5. **Access the app**

   Open your browser at:

