# Section 03 | Databases + SQL Fundamentals

<span style="color: #ED7D31;">**ZtM Academy | Complete SQL + Databases Bootcamp | Zero to Mastery**</span>

#### Lessons
- SQL Playground
- What Is SQL?
- What Is A Query?
- Exercise: Setting Up Your First Database

### [Db-Fiddle](https://www.db-fiddle.com/)
<span style="color: #3c9dff;">An SQL playground and online database management system.</span>

### What Is SQL?
SQL (Structured Query Language) is the standard programming language used to manage, manipulate, and retrieve data stored in relational database management systems. Most modern relational databases, such as PostgreSQL, MySQL, and SQL Server, use SQL as their primary interface.

### What Is a Database?
A database is an organized collection of structured information, or data, which allows efficient storage, modification, and retrieval of large volumes of information across various applications. It is managed by a Database Management System (DBMS), which serves as the software interface for interacting with the data.

### What Is a Query?
An **SQL query** is a specific **SQL statement** designed to manipulate or retrieve data. It uses **clauses** (query parts) to provide structure. Each clause begins with a **keyword** (like `SELECT`) and **identifiers** represent the names of tables or columns. Furthermore, **expressions** and **conditions** are used for **filtering** the dataset to return only the relevant rows.

```sql
-- This is an SQL comment: fetching premium users.
SELECT user_name -- this is a clause
-- 'SELECT' is a keyword; 'user_name' is an identifier
FROM users -- this is a clause
-- 'FROM' is a keyword; 'users' is an identifier
WHERE (5 + 10) < login_count>; -- this is a filtering clause
-- 'WHERE' is a keyword; '(5 + 10)' is an expression; '(5 + 10) < login_count' is a condition
```

### [Db-Fiddle > Query Exercise](https://www.db-fiddle.com/f/7fnLq7sZNknYPfm6U2xEAH/0)
### [Db-Fiddle > Query Solution](https://www.db-fiddle.com/f/sTq8m5ty2h8RdP3YRJqB9L/0)

## Lesson Title

## Lesson Title

---
