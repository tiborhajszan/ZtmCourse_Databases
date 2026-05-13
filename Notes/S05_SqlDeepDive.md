# Section 05 | SQL Deep Dive

<span style="color: #ED7D31;">**ZtM Academy | Complete SQL + Databases Bootcamp | Zero to Mastery**</span>

#### Lessons
- Query Along
- Starting With Query
- Exercise: Simple Queries
- Changing Column Names in a SELECT Query
- Concat Function
- What Is A Function In SQL?
- Aggregate Functions

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

### SQL Functions
- **Aggregate Functions:** Combine multiple records (e.g., all values in a column) and return a single aggregated value (e.g., `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`).
- **Scalar Functions:** Like the `map()` function in Python, they operate on each record individually and return multiple corresponding values (e.g., `CONCAT()`, `LENGTH()`, `UPPER()`).

### `CONCAT()` Function
```sql
-- concatenating columns
SELECT CONCAT("column1", ' ', "column2") AS "concatenated_column" FROM "schema"."table";
```

### Aggregate Function Examples
```sql
-- calculating the average of a set of values
SELECT AVG("column") FROM "schema"."table";

-- counting the total number of records in a column
SELECT COUNT("column") FROM "schema"."table";

-- finding the minimum value in a set of values
SELECT MIN("column") FROM "schema"."table";

-- finding the maximum value in a set of values
SELECT MAX("column") FROM "schema"."table";

-- calculating the sum of a set of values
SELECT SUM("column") FROM "schema"."table";
```

## Resources

### [PostgreSQL Documentation > Aggregate Functions](https://www.postgresql.org/docs/12/functions-aggregate.html)
<span style="color: #3c9dff;">Reference for aggregate functions available in PostgreSQL.</span>

---
