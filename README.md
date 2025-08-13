# 📚 Online Bookstore SQL Project

## 📌 Overview
This project is a **PostgreSQL-based database** for an **online bookstore**.  
It demonstrates **database design**, **data import from CSV files**, and **various SQL queries** for basic operations and advanced analytics.

The project is perfect for **learning and practicing SQL** concepts such as:
- Database & table creation
- Data importing
- Filtering, grouping, and aggregations
- JOIN operations
- Analytical queries

---

## 🗂 Database Structure

**Database Name:** `BookstoreDB`

| Table Name       | Description                                |
|------------------|--------------------------------------------|
| `tbl_books`      | Stores details about books in the store    |
| `tbl_customers`  | Contains customer information              |
| `tbl_orders`     | Holds order transactions and purchase data |

---

## 📦 Tables & Columns

### 1️⃣ **tbl_books**
| Column Name       | Type          | Description              |
|-------------------|--------------|--------------------------|
| `id`              | SERIAL (PK)  | Book ID                  |
| `title`           | VARCHAR(120) | Book title               |
| `author_name`     | VARCHAR(100) | Author's name            |
| `category`        | VARCHAR(60)  | Genre or category        |
| `year_published`  | INT          | Year of publication      |
| `unit_price`      | NUMERIC      | Price of the book        |
| `stock_count`     | INT          | Stock available          |

### 2️⃣ **tbl_customers**
| Column Name       | Type          | Description              |
|-------------------|--------------|--------------------------|
| `id`              | SERIAL (PK)  | Customer ID              |
| `full_name`       | VARCHAR(100) | Customer's full name     |
| `email_address`   | VARCHAR(120) | Email address            |
| `contact_no`      | VARCHAR(15)  | Contact number           |
| `city`            | VARCHAR(50)  | City of residence        |
| `country`         | VARCHAR(100) | Country of residence     |

### 3️⃣ **tbl_orders**
| Column Name       | Type          | Description              |
|-------------------|--------------|--------------------------|
| `id`              | SERIAL (PK)  | Order ID                 |
| `customer_id`     | INT (FK)     | Linked to `tbl_customers`|
| `book_id`         | INT (FK)     | Linked to `tbl_books`    |
| `order_date`      | DATE         | Date of order            |
| `quantity`        | INT          | Number of copies ordered |
| `total_cost`      | NUMERIC      | Total price for the order|

---

## 📂 Project Files
```
📁 SQL_Project
│── 📄 bookstore_project.sql     # Main SQL script
│── 📄 Books.csv                 # Sample books data
│── 📄 Customers.csv             # Sample customers data
│── 📄 Orders.csv                # Sample orders data
│── 📄 README.md                 # Project documentation
```

---

## 🛠 How to Run

1. **Create Database**
```sql
CREATE DATABASE BookstoreDB;
\c BookstoreDB;
```

2. **Run SQL Script**
```sql
\i 'bookstore_project.sql';
```

3. **Verify Tables**
```sql
SELECT * FROM tbl_books;
SELECT * FROM tbl_customers;
SELECT * FROM tbl_orders;
```

4. **Run Queries**
- Basic filters
- Aggregations
- Joins
- Analytical reports

---

## 📊 Example Queries

- **List all books in Fiction category**
```sql
SELECT * FROM tbl_books WHERE category = 'Fiction';
```

- **Find the highest-priced book**
```sql
SELECT * FROM tbl_books ORDER BY unit_price DESC LIMIT 1;
```

- **Top 3 costliest Fantasy books**
```sql
SELECT * FROM tbl_books WHERE category = 'Fantasy' ORDER BY unit_price DESC LIMIT 3;
```

- **Total revenue generated**
```sql
SELECT SUM(total_cost) AS revenue FROM tbl_orders;
```

---

## 🚀 Skills Practiced
- SQL Schema Design
- Data Importing (CSV → Database)
- Data Filtering
- GROUP BY & Aggregations
- JOIN Queries
- Advanced SQL Reporting

---

## 📌 Author
👤 Piyush Verma
📧 pv535111@gmail.com

---

✅ This project can be extended with:
- Stored procedures
- Views
- Triggers
- More analytical dashboards
