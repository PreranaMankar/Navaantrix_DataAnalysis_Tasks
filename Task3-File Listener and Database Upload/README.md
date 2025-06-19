# 📁 Task 3 – File Listener and Database Upload

This project implements a Python-based **file monitoring system** using `watchdog`, which **listens for new CSV files** in a specified folder and **automatically uploads** their contents into a **SQLite database**.

---

## 🔧 Technologies Used

- **Pandas** – for reading CSVs
- **Watchdog** – to monitor file changes
- **SQLAlchemy** – for interacting with SQLite
- **SQLite** – as the local database

---

## 📂 Folder Structure

Task3-File Listener and Database Upload/
├── monitored_folder/ # Folder being watched
├── working script/ # Folder having below files
├── uploaded_data.db # SQLite database (auto-generated)
├── file_listener_uploader.ipynb # Jupyter notebook with working code
└── README.md # This file

---

## ⚙️ How It Works

1. **Watchdog** monitors a folder for `.csv` file creation.
2. When a new file is added:
   - It reads the CSV using `pandas`.
   - Uploads it to the SQLite database `uploaded_data.db` into table `sales_data`.
3. The script runs continuously and handles each new file.

---
## Check the database:
import sqlite3
conn = sqlite3.connect("uploaded_data.db")
pd.read_sql_query("SELECT * FROM sales_data", conn)
