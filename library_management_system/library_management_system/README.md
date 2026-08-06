# Library Management System (Python + MySQL)

A command-line Library Management System built with Python and MySQL. It manages books, members, and issue/return transactions using a normalized relational database, and includes a basic analytics report.

## Features
- Add and view books (with available/total copy tracking)
- Add and view members
- Issue and return books, with automatic copy-count updates
- Full transaction history
- Report: most borrowed books

## Tech Stack
- **Python 3** — application logic
- **MySQL / MySQL Workbench** — database design and management
- **mysql-connector-python** — database connectivity

## Database Schema
Three related tables:
- `books` (book_id, title, author, genre, total_copies, available_copies)
- `members` (member_id, name, email, phone)
- `transactions` (transaction_id, book_id, member_id, issue_date, return_date, status)

`transactions` references both `books` and `members` via foreign keys.

## Setup

1. **Create the database**
   Open MySQL Workbench and run the script in `schema.sql`.

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure your database credentials**
   Edit `db_connection.py` and update the `DB_CONFIG` dictionary with your MySQL username/password.

4. **Run the app**
   ```bash
   python main.py
   ```

## Project Structure
```
library_management_system/
├── schema.sql              # Database schema (run in MySQL Workbench)
├── db_connection.py        # MySQL connection handler
├── library_operations.py   # Core CRUD + business logic
├── main.py                 # CLI entry point
├── requirements.txt
└── README.md
```

## Possible Extensions
- Tkinter or PyQt GUI
- Fine calculation for overdue books
- Login system for members vs. admin
- Export reports to CSV/Excel

## Resume Bullet Example
> Built a Library Management System using Python and MySQL, implementing CRUD operations, foreign-key relationships, and reporting queries to track book circulation.
