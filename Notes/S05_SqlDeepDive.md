# Section 05 | SQL Deep Dive

<span style="color: #ED7D31;">**ZtM Academy | Complete SQL + Databases Bootcamp | Zero to Mastery**</span>

#### Lessons
- Query Along
- Starting With Query
- Exercise: Simple Queries
- Changing Column Names in a SELECT Query
- Concat Function

### SQL Command Categories
SQL commands are organized into functional groups including
- **DCL** (Data Control Language) for managing permissions,
- **DDL** (Data Definition Language) for defining structures,
- **DML** (Data Manipulation Language) for modifying records,
- **DQL** (Data Query Language) for fetching data.

### Data Retrieval
- **Role of DQL:** The Data Query Language is centered around the `SELECT` statement, which is the most frequently used command in SQL.
- **Purpose of `SELECT`:** The primary purpose of the `SELECT` statement is to retrieve data from a database without changing the underlying data.

### `SELECT` Syntax
```sql
-- returning all data from a table
SELECT * FROM "schema"."table";

-- returning specific columns from a table
SELECT "column1", "column2" FROM "schema"."table";

-- returning specific columns from a table with aliases
SELECT "column1" AS "alias1", "column2" AS "alias2" FROM "schema"."table";
```

### `CONCAT` Function
```sql
-- concatenating columns
SELECT CONCAT("column1", "column2") AS "concatenated_column" FROM "schema"."table";
```

## Lesson Title

<span style="color: #3c9dff;">Resource explanation.</span>

---
