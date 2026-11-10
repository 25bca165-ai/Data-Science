# Library Management System

**Project Type:** DBMS Mini Project  
**Course:** Bachelor of Computer Applications (BCA)  
**Database:** MySQL  
**Database Name:** `librarydb`  
**Software:** MySQL Workbench  

## 1. Introduction

The Library Management System is a small database project built with MySQL. It stores information about library members, books and book-borrowing records.

The project is intended to practise relational database design and SQL operations. The stored records can be used to review borrowing activity, identify books that are currently issued and calculate fines for late returns.

## 2. Database Tables

The database contains three tables.

### Members

Stores basic details about students and faculty members.

| Column | Description |
|---|---|
| `member_id` | Primary key; automatically generated |
| `member_name` | Name of the member |
| `member_type` | Student or Faculty |
| `joined_date` | Date the member joined |

### Books

Stores the books listed in the library.

| Column | Description |
|---|---|
| `book_id` | Primary key; automatically generated |
| `title` | Book title |
| `author` | Book author |
| `category` | Book category |
| `price` | Book price |
| `copies_available` | Number of copies available |

### Issues

Stores each book-borrowing transaction.

| Column | Description |
|---|---|
| `issue_id` | Primary key; automatically generated |
| `member_id` | Foreign key referencing `members` |
| `book_id` | Foreign key referencing `books` |
| `issue_date` | Date the book was issued |
| `due_date` | Expected return date |
| `return_date` | Actual return date; `NULL` while not returned |

## 3. Database Relationships

- One member can have many issue records.
- One book can appear in many issue records.
- The `issues` table connects members and books through foreign keys.

## 4. Sample Data

The revised sample dataset contains:

| Table | Records |
|---|---:|
| Members | 12 |
| Books | 15 |
| Issues | 32 |

The records include Student and Faculty members and books from Programming, Database, Networking, Biography, Fiction, Science and Mathematics categories.

## 5. Fine Calculation Rules

The project uses a late-return fine of **₹2 per day**.

**Fine = Number of late days × ₹2**

- Student borrowing period: 14 days.
- Faculty borrowing period: 30 days.
- A book returned after its due date is treated as late.
- A book returned on or before its due date has no fine.
- A `NULL` return date means the book is still issued.

## 6. SQL Concepts Practised

The project can be used to practise:

1. Creating databases and tables
2. Primary keys and foreign keys
3. `SELECT`, `WHERE` and `ORDER BY`
4. Aggregate functions such as `COUNT()` and `SUM()`
5. `GROUP BY` and `HAVING`
6. `INNER JOIN` and `LEFT JOIN`
7. Subqueries
8. Handling `NULL` values
9. `DATEDIFF()`
10. Window functions such as `RANK()`
11. Stored procedures
12. Triggers

## 7. Project Questions

The project is organised into four phases.

**Phase 1 – Database Basics**
- C1: Draw the Entity Relationship Diagram.
- C2: Find the total number of members, books and issue records.

**Phase 2 – SQL Queries**
- C3: Find the number of titles and available copies in each category.
- C4: Find the five most borrowed books.
- C5: Identify members who have never borrowed a book.
- C6: Display currently issued books with member names and due dates.
- C7: Find late returns and calculate their fines.
- C8: Calculate the total fine for each member.
- C9: Compare borrowing activity between students and faculty.
- C10: Rank members by the number of books borrowed.
- C11: Identify the most popular book category.
- C12: Find books with zero available copies and pending issues.

**Phase 3 – Database Automation**
- C13: Create a stored procedure to display a member's borrowing history.
- C14: Create a trigger to reduce available copies when a new issue is inserted.

**Phase 4 – Conclusion**
- C15: Suggest improvements to library management based on the query results.

## 8. Files Included

| File | Description |
|---|---|
| `library_management.sql` | Creates the database and its three tables. |
| `sample_data.sql` | Inserts the revised sample records. |
| `ERD.png` | Entity Relationship Diagram. |

## 9. How to Run the Project

1. Open MySQL Workbench and connect to your MySQL server.
2. Open and execute `library_management.sql`.
3. Open and execute `sample_data.sql`.
4. Run the following statements to check that the records were inserted:

```sql
USE librarydb;

SELECT COUNT(*) FROM members;
SELECT COUNT(*) FROM books;
SELECT COUNT(*) FROM issues;
```

Expected record counts:

- Members: 12
- Books: 15
- Issues: 32

Run the project queries after loading the schema and sample data.

## 10. Learning Outcomes

This project provides practice with relational tables, primary and foreign keys, joins, aggregate functions, subqueries and date calculations. It also introduces database automation using stored procedures and triggers.

## 11. Conclusion

The Library Management System shows how a relational database can organise library members, book details and borrowing transactions. Its sample records provide a base for practising SQL queries and analysing library activity.

## 12. Adaptation Note

This copy contains a revised sample dataset and rewritten project documentation. The database schema and ER diagram have been retained from the original project, so this version should be treated as an adaptation rather than an independently designed schema.
"# Data-Science" 
