# Flask User Authentication System

A simple yet secure user authentication system built with Python (Flask), HTML, CSS, and SQLite. This project demonstrates a clear login workflow with server-side validation and a minimal, user-friendly interface.

## Features

- Username and password authentication
- Flask backend with clean, efficient routing
- Lightweight SQLite database for user storage
- Responsive and accessible login page
- Real-time feedback with flash messages
- Modular and maintainable codebase

## Technology Stack

- **Backend:** Python 3.x, Flask
- **Frontend:** HTML5, CSS3
- **Database:** SQLite
- **Tools:** Git, VS Code (recommended)

## Project Structure

```
flask_user_auth/
│
├── app.py              # Flask app source code
├── users.db            # SQLite database file
├── init_db.py          # Database initialization script
│
├── templates/          # HTML templates
│   └── login.html
│
└── static/             # Static files
    └── style.css
```

## Prerequisites

- Python 3.6 or newer
- Pip package manager
- Basic command line knowledge

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/your-username/flask_user_auth.git
cd flask_user_auth
```

### 2. Install dependencies

```bash
pip install flask
```

### 3. Initialize the database

Create a file called `init_db.py` with this content:

```python
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
```

Run the script:

```bash
python init_db.py
```

### 4. Run the Flask app

```bash
python app.py
```

### 5. Open your browser

Navigate to:

```
http://127.0.0.1:5000
```

## Usage

- Log in with the default user:
  - **Username:** `admin`
  - **Password:** `1234`
- A successful login shows a personalized welcome message
- Incorrect login attempts display error messages

## Security Notice

⚠️ **This project is for educational use only.** Storing passwords in plaintext is unsafe and not recommended for production.

For production systems, you should:

- Use password hashing (`werkzeug.security.generate_password_hash`)
- Employ secure session management
- Use environment variables for sensitive configuration
- Deploy over HTTPS
- Implement CSRF protection
- Add rate limiting for login attempts

## Future Improvements

- [ ] User registration and password recovery
- [ ] Password hashing and salting
- [ ] Session expiration and logout functionality
- [ ] Role-based access control (RBAC)
- [ ] UI improvements with modern frameworks
- [ ] Automated testing and input validation
- [ ] Remember me functionality
- [ ] Email verification

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Flask documentation and community
- SQLite for lightweight database functionality
- All contributors and supporters of this project

## Contact

Your Name - [@your_twitter](https://twitter.com/your_twitter) - your.email@example.com

Project Link: [https://github.com/your-username/flask_user_auth](https://github.com/your-username/flask_user_auth)

---

**Made with ❤️ for learning purposes**
