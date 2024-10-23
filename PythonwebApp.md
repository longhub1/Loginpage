Here’s the content shared in proper Markdown format:

```markdown
# Login Page with SQL Database

## Overview
This project demonstrates a simple **Login Page** application integrated with a **MySQL Database**. The project is designed using Python, leveraging a web framework to handle user authentication, and securely storing user data in a SQL database.

## Table of Contents
- [Requirements](#requirements)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Database Setup](#database-setup)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Requirements
Ensure you have the following software installed:
- **Python 3.12** or higher
- **MySQL Server**
- **pip** (Python package installer)
- A Linux-based environment (Ubuntu is recommended, but others are supported)

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Fir3eye/Login-Page-DB.git
   cd Login-Page-DB/
   ```

2. **Create a Virtual Environment** (recommended)
   ```bash
   sudo apt update
   sudo apt install python3.12-venv
   python3 -m venv myenv
   source myenv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Project Structure
```
Login-Page-DB/
│
├── app.py                # Main application file
├── requirements.txt      # Python dependencies
├── templates/            # HTML templates for the login page
├── static/               # CSS and JavaScript files
└── config.py             # Configuration file (database credentials)
```

## Configuration

1. **MySQL Configuration**:
   Update the MySQL configuration file if needed:
   ```bash
   sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
   ```
   
2. **Set MySQL User Credentials**:
   Use the following commands to set up the MySQL root user:
   ```sql
   sudo mysql
   ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password';
   FLUSH PRIVILEGES;
   ```

3. **Update Database Credentials** in the `config.py` file:
   ```python
   DB_HOST = 'localhost'
   DB_USER = 'root'
   DB_PASSWORD = 'your_password'
   DB_NAME = 'login_db'
   ```

## Running the Application

To start the application, run:
```bash
python3 app.py
```
The app should be accessible at `http://localhost:5000`.

## Database Setup

1. **Start MySQL Server**
   ```bash
   sudo systemctl start mysql
   sudo systemctl enable mysql
   ```

2. **Create Database and Table**:
   Connect to MySQL and execute:
   ```sql
   CREATE DATABASE login_db;
   USE login_db;
   
   CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       username VARCHAR(50) NOT NULL,
       password VARCHAR(255) NOT NULL
   );
   ```

## Usage

1. **Register**: Open the `/register` endpoint in your web browser to create a new user.
2. **Login**: Use the `/login` endpoint to authenticate with your credentials.
3. **Dashboard**: Successful login redirects to a simple dashboard.

## Troubleshooting

- If you encounter `ModuleNotFoundError`, ensure all dependencies are installed with `pip install -r requirements.txt`.
- MySQL connection errors may require checking your `config.py` for accurate database credentials.
- Use `sudo systemctl status mysql` to verify that the MySQL server is running.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any suggestions or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```

Feel free to copy and paste this Markdown directly into your file!
