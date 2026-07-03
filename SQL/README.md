# Digital Library Management System

## Overview

The Digital Library Management System is a MySQL database project that manages books, students, and book issue records. It demonstrates the use of relational database concepts, including table creation, primary and foreign keys, data insertion, updates, joins, aggregation, and CRUD operations.

---

## Features

- Manage book information.
- Store student records.
- Track issued and returned books.
- Identify overdue books.
- Generate category-wise issue statistics.
- Update student activity.
- Remove inactive students.

---

## Database Structure

### Database

```
digital_lib
```

### Tables

#### Books

Stores information about books.

| Column | Data Type |
|---------|-----------|
| book_id | INT (Primary Key, Auto Increment) |
| title | VARCHAR(100) |
| author | VARCHAR(100) |
| published_date | DATE |
| pages | INT |
| category | VARCHAR(100) |

---

#### Students

Stores student information.

| Column | Data Type |
|---------|-----------|
| stu_id | INT (Primary Key, Auto Increment) |
| name | VARCHAR(100) |
| email | VARCHAR(100) (Unique) |
| enrollment_date | DATE |
| last_active | DATE |

---

#### IssuedBooks

Stores book issue records.

| Column | Data Type |
|---------|-----------|
| issued_id | INT (Primary Key, Auto Increment) |
| book_id | INT (Foreign Key) |
| student_id | INT (Foreign Key) |
| issue_date | DATE |
| return_date | DATE |

---

## Relationships

- One student can issue multiple books.
- One book can be issued multiple times.
- Foreign Keys:
  - `book_id` references `books(book_id)`
  - `student_id` references `students(stu_id)`

---

## Sample Data

The project includes sample records for:

- Books
- Students
- Issued Books

to demonstrate various SQL operations.

---

## SQL Operations Performed

### Database Creation

- Create database
- Select database

### Table Creation

- Books
- Students
- IssuedBooks

### CRUD Operations

#### Create
- Insert books
- Insert students
- Insert issued books

#### Read
- Display all books
- Display all students
- Display all issued books

#### Update
- Add `last_active` column
- Update student activity
- Update activity based on issued books

#### Delete
- Remove inactive students (inactive for more than 3 years)

---

## Queries Included

### 1. Find Overdue Books

Displays books that have not been returned within 14 days.

```sql
SELECT *
FROM issuedbooks
WHERE return_date IS NULL
AND issue_date < CURRENT_DATE - INTERVAL 14 DAY;
```

---

### 2. Category-wise Book Issue Count

Displays the number of books issued in each category.

```sql
SELECT b.category, COUNT(*) AS total_issued
FROM issuedbooks ib
JOIN books b
ON ib.book_id = b.book_id
GROUP BY b.category
ORDER BY total_issued DESC;
```

---

### 3. Delete Inactive Students

Deletes students whose last activity was more than three years ago.

```sql
DELETE FROM students
WHERE last_active < CURRENT_DATE - INTERVAL 3 YEAR;
```

---

### 4. Update Student Activity

Updates the `last_active` column based on currently issued books or latest returned book.

```sql
UPDATE students
SET last_active = ...
```

---

## Concepts Used

- DDL (CREATE, ALTER)
- DML (INSERT, UPDATE, DELETE)
- SELECT Queries
- INNER JOIN
- Aggregate Functions
- GROUP BY
- ORDER BY
- Foreign Keys
- Primary Keys
- Constraints
- CASE Statement
- EXISTS
- COALESCE
- Subqueries
- Date Functions

---

## Requirements

- MySQL 8.0 or above
- MySQL Workbench (optional)

---

## How to Run

1. Open MySQL Workbench.
2. Create a new SQL script.
3. Copy and paste the SQL code.
4. Execute the script.
5. Run the SELECT queries to verify the data.

---

## Expected Outcome

The project successfully demonstrates:

- Library database creation
- Student management
- Book issue tracking
- Overdue book identification
- Category-wise reporting
- Student activity management
- Data maintenance using SQL

---

## Author

**Rithwik Burri**
