# Section 03 | Databases + SQL Fundamentals

<span style="color: #ED7D31;">**ZtM Academy | Complete SQL And Databases Bootcamp | Zero to Mastery**</span>

#### Lessons
- SQL Playground
- What Is SQL?
- What Is A Query?
- Exercise: Setting Up Your First Database
- Imperative vs Declarative
- History of SQL
- Exercises: The Select Statement
- Optional: History of SQL Deep Dive
- SQL Standards
- What Is A Database? Revisited

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

### Imperative Programming
Imperative programming is a coding paradigm where the developer provides the computer with a specific sequence of steps to reach a desired outcome. It focuses on **how** a task should be performed by explicitly describing the logic of the program. **Examples of Imperative Languages:** C++, Java, Python.

### Declarative Programming
Declarative programming is a coding paradigm where you describe **what** you want to achieve rather than providing a specific sequence of instructions on how to do it. The underlying system or language handles the "how" (the specific logic and control flow) freeing the developer to focus on the desired outcome. **Examples of Declarative Languages:** SQL, HTML, CSS.

### Evolution of Databases and SQL
The journey of computerized data management began in the mid-1960s with the transition from the flat file data storage model to IBM’s hierarchical model and Charles Bachman’s network model at GE. This landscape shifted dramatically in 1970 when IBM’s Ted Codd and CJ Date introduced the relational model, which Michael Stonebraker used to develop the INGRES database at Berkeley in 1973. By 1975, IBM researchers Don Chamberlin and Raymond Boyce developed the SQL language (originally SEQUEL) for IBM’s System R to bring the relational theory to life, eventually leading Larry Ellison, Bob Miner, and Ed Oates to release Oracle in 1979, followed by IBM’s own DB2 in 1983.

### [W3 Schools > SQL Exercises](https://www.w3schools.com/sql/sql_exercises.asp)

### [YouTube > History of Databases](https://www.youtube.com/watch?v=KG-mqHoXOXY)

### SQL Standardization

Standardization is the process of establishing a common set of technical rules, known as standards, to ensure that different systems can work together reliably. In the context of SQL, official standards are maintained by organizations like ANSI and ISO to provide a consistent blueprint for the language across different database vendors. While these standards ensure core portability, many vendors add proprietary extensions—often called dialects—to provide specialized functionality that goes beyond the official requirements.

### Limitations of the Flat File Model

The flat file model is severely limited by data redundancy and a lack of relationships, as information must be duplicated across multiple files rather than linked efficiently. Because every program must manage its own file structure, these systems also struggle with data integrity and offer no built-in way to handle concurrent access by multiple users. This lack of centralized control makes searching and updating data a slow, manual process that is highly prone to errors.

## Lesson Title

## Lesson Title

---
