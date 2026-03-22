# 📚 SMART LIBRARY INVENTORY SYSTEM

A modern, full-featured library management system built with Flask and Oracle Database. Manage book inventory, user authentication, borrowing/returning books, and generate comprehensive reports with ease.

---

## ✨ Features

- **👤 User Authentication**
  - User registration with email verification
  - Secure login with password hashing
  - Role-based access control (Admin & Student)
  - Email notifications for book transactions

- **📖 Book Management**
  - View all books with real-time availability status
  - Add new books to inventory (Admin only)
  - Track book details (ISBN, Title, Category, Publisher)
  - Monitor borrowed vs. available books

- **🔄 Borrow & Return System**
  - Seamless book checkout process
  - Automatic due date calculation (7 days)
  - Return tracking with status updates
  - Email notifications on every transaction

- **🔍 Smart Search**
  - Search books by title, ISBN, or category
  - Quick filters for availability status
  - Advanced reporting capabilities

- **📊 Dashboard & Reports**
  - Real-time dashboard with key metrics
  - Total books, available, and borrowed statistics
  - Exportable reports (CSV format)
  - User activity tracking

- **🎨 Responsive UI**
  - Modern and intuitive interface
  - Mobile-friendly design
  - Error handling with user-friendly messages
  - Flash notifications for all actions

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Backend** | Flask 3.1.3 |
| **Database** | Oracle Database (XEPDB1) |
| **Frontend** | HTML5, CSS3, Jinja2 |
| **Authentication** | Werkzeug Security |
| **Email** | Flask-Mail (SMTP) |
| **Additional** | SQLAlchemy, WTForms |

---

## 📋 Requirements

- Python 3.8+
- Oracle Database (with XEPDB1 service)
- Gmail account (for email notifications)

All Python dependencies are listed in `requirements.txt`

---

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/codeWithAnika/SMART-LIBRARY-INVENTORY-SYSTEM-.git
cd LIBRARYDB
```

### 2. Create Virtual Environment
```bash
python -m venv venv

# On Windows (PowerShell)
.\venv\Scripts\Activate.ps1

# On Windows (CMD)
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Database Connection
Update the database credentials in `app.py`:
```python
def get_db_connection():
    dsn = oracledb.makedsn("localhost", 1521, service_name="XEPDB1")
    return oracledb.connect(user="LIBDB", password="your_password", dsn=dsn)
```

### 5. Configure Email Notifications
Update Gmail credentials in `app.py`:
```python
app.config['MAIL_USERNAME'] = 'your-email@gmail.com'
app.config['MAIL_PASSWORD'] = 'your-app-specific-password'
```

> 💡 **Tip:** Generate an app-specific password from your Google Account settings: https://myaccount.google.com/apppasswords

### 6. Run the Application
```bash
python app.py
```

The application will be available at `http://localhost:5000`

---

## 📱 Screenshots

### Dashboard
![Dashboard](./screenshots/dashboard.png)
*Real-time overview of library statistics and book inventory*

### Book Listing
![Books Page](./screenshots/books.png)
*View all books with availability status and borrower information*

### Add Book
![Add Book](./screenshots/add-book.png)
*Admin interface to add new books to inventory*

### Login Page
![Login](./screenshots/login.png)
*Secure user authentication*

### Registration
![Register](./screenshots/register.png)
*New user registration with email and department*

### Search & Filter
![Search](./screenshots/search.png)
*Advanced search and filtering capabilities*

### Reports
![Reports](./screenshots/reports.png)
*Generate and export library reports*

---

## 🔐 User Roles

### 👨‍💼 Admin
- Add new books to the system
- View all users and their borrowing history
- Generate comprehensive reports
- Manage system settings

### 👨‍🎓 Student
- View available books
- Borrow and return books
- Check borrowing history
- View personal account information

---

## 📊 Database Schema Highlights

- **LIB_USER**: User accounts and profiles
- **BOOK**: Book inventory and metadata
- **BORROW**: Borrowing transactions and history
- **CATEGORY**: Book categorization
- **PUBLISHER**: Publisher information

---

## 🎯 API Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/` | Home page | No |
| GET/POST | `/register` | User registration | No |
| GET/POST | `/login` | User login | No |
| GET | `/logout` | User logout | Yes |
| GET | `/dashboard` | Dashboard | Yes |
| GET | `/books` | View all books | Yes |
| POST | `/add-book` | Add new book | Yes (Admin) |
| POST | `/checkout_book/<id>` | Borrow book | Yes |
| POST | `/return_book/<id>` | Return book | Yes |
| GET | `/search` | Search books | Yes |
| GET | `/reports` | View reports | Yes (Admin) |

---

## 🐛 Troubleshooting

### Database Connection Error
- Ensure Oracle Database is running
- Verify service name (XEPDB1)
- Check username and password

### Email Not Sending
- Enable "Less secure app access" or use app-specific password
- Verify Gmail SMTP settings
- Check internet connectivity

### Import Errors
- Ensure all packages in `requirements.txt` are installed
- Verify Python version compatibility (3.8+)

---

## 📝 Project Structure

```
LIBRARYDB/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── README.md             # This file
├── templates/            # HTML templates
│   ├── base.html         # Base template
│   ├── navbar.html       # Navigation bar
│   ├── dashboard.html    # Dashboard
│   ├── books.html        # Book listing
│   ├── add_book.html     # Add book form
│   ├── search.html       # Search page
│   ├── reports.html      # Reports page
│   ├── login.html        # Login page
│   ├── register.html     # Registration page
│   ├── 404.html          # Error page
│   └── 500.html          # Server error page
└── instance/             # Instance configuration
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Anika Talavadekar**
- GitHub: [@codeWithAnika](https://github.com/codeWithAnika)
- Email: anikatalavadekar@gmail.com

---

## 📞 Support

For support, email anikatalavadekar@gmail.com or open an issue on GitHub.

---

## 🎉 Acknowledgments

- Flask documentation and community
- Oracle Database support
- Flask-Mail for email integration
- All contributors and users

---

**Made with ❤️ by Anika Talavadekar**
