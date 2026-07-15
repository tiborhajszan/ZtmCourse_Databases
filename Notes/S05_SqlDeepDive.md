<span style="color: #ED7D31;">**ZtM Academy | Complete SQL and Databases Bootcamp | Zero to Mastery**</span>

# Section 05 | SQL Deep Dive

#### Lessons
- Query Along
- Starting With Query
- Exercise: Simple Queries
- Changing Column Names in a SELECT Query
- Concat Function
- What Is A Function In SQL?
- Aggregate Functions
- Exercise: Aggregate Functions
- Commenting Your Queries
- Common SELECT Mistakes
- Filtering Data
- AND and OR
- Exercise: Filtering Data
- The NOT Keyword
- Exercise: The Where Clause
- Comparison Operators
- Exercise: Comparison Operators
- Logical Operators
- Operator Precedence
- Operator Precedence 2
- Operator Precedence Extra
- Exercise: Operator Precedence
- Checking For NULL Values
- IS Keyword
- NULL Coalescing
- Exercise: Null Value Coalescing
- 3 Valued Logic
- Exercise: 3 Valued Logic
- BETWEEN + AND
- Exercise: BETWEEN + AND
- IN Keyword
- Exercise: IN Keyword
- LIKE
- Exercise: Like Keyword
- Dates And Timezones
- Setting Up Timezones
- How Do We Format Date And Time?
- Timestamps
- Date Functions
- Date Difference And Casting
- Age Calculation
- Extracting Information
- Intervals
- Exercise: Date and Timestamp
- DISTINCT
- Exercise: Distinct Keyword
- Sorting Data
- Exercise Sorting Data
- Multi Table SELECT
- Inner Join
- Self Join
- Outer Join

### SQL Command Categories
- **DCL** (Data Control Language) for managing permissions.
- **DDL** (Data Definition Language) for defining structures.
- **DML** (Data Manipulation Language) for modifying records.
- **DQL** (Data Query Language) for fetching data.

### Data Retrieval
- **Role of DQL:** The Data Query Language is centered around the `SELECT` statement, which is the most frequently used command in SQL.
- `SELECT`: Retrieves information from a database without changing the underlying data.

### SELECT Keyword
```sql
-- returning all data from a table
SELECT * FROM "schema"."table";
-- returning specific columns from a table
SELECT "column1", "column2" FROM "schema"."table";
-- returning specific columns from a table with aliases
SELECT "column1" AS "alias1", "column2" AS "alias2" FROM "schema"."table";
```

### SQL Functions
- **Aggregate Functions:** Take multiple records (e.g., all values in a column) and compute a single aggregated value from them.
- **Scalar Functions:** Like the `map()` function in Python, they operate on each record individually and return multiple corresponding values (e.g., `CONCAT()`, `LENGTH()`, `UPPER()`).

### Aggregate Functions<br><br>

```sql
-- calculating sum of field/column
SELECT SUM("column") FROM "schema"."table";
-- counting number of records in field/column
SELECT COUNT("column") FROM "schema"."table";
-- calculating average of field/column
SELECT AVG("column") FROM "schema"."table";
-- finding minimum value in field/column
SELECT MIN("column") FROM "schema"."table";
-- finding maximum value in field/column
SELECT MAX("column") FROM "schema"."table";
```

### CONCAT() Function
```sql
-- concatenating columns
SELECT CONCAT("column1", ' ', "column2") AS "concatenated_column" FROM "schema"."table";
```

### SQL Comments
```sql
-- this is a single-line comment
/*
this is a
multi-line comment
*/
```

### Common SELECT Mistakes
- **Misspelling:** Column names, table names, schema names, or any identifier.
- **Invalid Column Names:** A column name should follow the rules of the SQL identifier naming convention. It should start with a letter, underscore, or dollar sign, and consist of alphanumeric characters, underscores, or dollar signs.
- **Single Quotes vs Double Quotes:** Single quotes are used for string literals, while double quotes are used for identifiers (column names, table names, schema names, etc.).
- **Commas vs Semicolons:** Commas are used to separate list items like multiple columns or multiple values, while semicolons are used to close individual SQL statements.

### Data Filtering
The primary purpose of most SQL queries is to retrieve only a subset of the data from a database. This is achieved through the `WHERE` keyword/clause, which allows you to specify the filtering criteria.<br><br>

```sql
-- filtering data
SELECT * FROM "schema"."table" WHERE "column" = 'value';
```

### SQL Logical Operators
- **`AND`:** Creates a conjunction of two conditions, i.e., returns only those records that satisfy both conditions. It basically narrows filtering results by applying two filters sequentially where the filter right to `AND` works on the output of the filter left to it.
- **`OR`:** Creates a disjunction of two conditions, i.e., returns all records that satisfy either condition. It basically widens filtering results by combining/merging the output of two separate filters.
- **`NOT`:** Negates a condition, i.e., returns all records that do not satisfy the condition. It basically inverts the output of the filter right after `NOT` by removing matching records from the dataset and returning the rest.<br><br>

```sql
-- filter chaining with AND
SELECT * FROM "schema"."table"
WHERE "column1" = 'value1' AND "column2" = 'value2';
-- filter combination with OR
SELECT * FROM "schema"."table"
WHERE "column1" = 'value1' OR "column1" = 'value2';
-- filter negation with NOT
SELECT * FROM "schema"."table"
WHERE NOT "column1" = 'value1' AND NOT "column1" = 'value2';
-- AND works on the filter combination within the parentheses
SELECT * FROM "schema"."table"
WHERE ("column1" = 'value1' OR "column1" = 'value2') AND "column3" = 'value3';
```

### SQL Comparison Operators
- **`=` :** Equal to.
- **`!=` or `<>` :** Not equal to.
- **`>` :** Greater than.
- **`<` :** Less than.
- **`>=` :** Greater than or equal to.
- **`<=` :** Less than or equal to.

### Query (`SELECT`) Operation Order
1. **FROM:** Starting with the full table/dataset.
2. **WHERE:** Filtering the dataset based on certain conditions.
3. **SELECT:** Returning the filtered records.

### Operator Precedence
1. **Parentheses `()`**
2. **Unary Plus `+`, Unary Minus `-`**
3. **Exponentiation `^`**
4. **Multiplication `*`, Division `/`, Modulo `%`**
5. **Addition `+`, Subtraction `-`**
6. **Comparison Operators `=`, `<>` or `!=`, `<`, `>`, `<=`, `>=`, `BETWEEN`, `IN`, `LIKE`, `IS NULL`, `IS NOT NULL`**
7. **NOT**
8. **AND**
9. **OR**

### Same Precedence Evaluation Order
- Operators at the same precedence level are evaluated left to right or right to left. Use parentheses to explicitly control evaluation order when needed.
- **Left-to-Right Evaluation:** `()`, `*`, `/`, `%`, `+`, `-`, string concatenation (`||`, `CONCAT()`), `=`, `<>`, `!=`, `<`, `>`, `<=`, `>=`, bitwise operators (`&`, `|`), `AND`, and `OR` follow left-to-right associativity when at the same precedence level.
- **Right-to-Left Evaluation:** unary `+`, unary `-`, `^`, and `NOT` follow right-to-left associativity when at the same precedence level.

### NULL Value
- **Empty Records:** Records that are not assigned a value are considered empty.
- **NULL Assignment:** Most database systems automatically assign a `NULL` value to empty records.
- **NULL Value:** `NULL` is neither zero nor an empty/blank string. It is a distinct marker representing the absence of value.
- **NULL Principles:**
  - Be **careful and defensive:** Allow `NULL` values only where it is absolutely necessary. Always check for and filter out `NULL` values in your queries.
  - Be **mindful and rational:** Consider the consequences of allowing `NULL` values. For example, do not allow `NULL` values for columns that are used in calculations or contain essential business information. But you can allow `NULL` values for columns that are optional or have default values.
  - Be **deliberate:** Make conscious decisions about `NULL` values and communicate them clearly to your team.
- ⚠️ <span style="color: #FF6B6B;">**Danger:**</span> `NULL` is dangerous because whatever operation you perform with `NULL`, the result will always be `NULL`, which may cause all sorts of issues in your applications.

### IS Keyword
The `IS` keyword is a special comparison operator that allows us to check for `NULL`, `TRUE`, or `FALSE` values, because the `=` operator cannot be used here. The `IS NOT` keyword is the opposite of the `IS` keyword. As a result, `IS NOT TRUE` is equivalent to `IS FALSE`, and `IS NOT FALSE` is equivalent to `IS TRUE`.<br><br>

```sql
-- checking for NULL values
SELECT * FROM "schema"."table" WHERE "column" IS NULL;
-- checking for TRUE values
SELECT * FROM "schema"."table" WHERE "boolean_column" IS TRUE;
SELECT * FROM "schema"."table" WHERE "boolean_column" IS NOT FALSE;
-- checking for FALSE values
SELECT * FROM "schema"."table" WHERE "boolean_column" IS FALSE;
SELECT * FROM "schema"."table" WHERE "boolean_column" IS NOT TRUE;
```

### NULL Coalescing
When working with datasets that may contain `NULL`, we should substitute `NULL` values with a default value using the `COALESCE()` function. The `COALESCE()` function returns the first non-`NULL` value from the list of its arguments.<br><br>

```sql
-- returning the first non-NULL value
SELECT COALESCE("column1", "column2", 'default_value') AS "result" FROM "schema"."table";
```

### Three Valued Logic
- **NULL Comparison:** `NULL` can not be compared to anything, including itself. When a boolean expression involves a `NULL` value, the outcome is always `NULL`.
- **Three Valued Logic:** Most programming languages use two-valued logic (`TRUE` and `FALSE`) and treat the `NULL` outcome of boolean expressions as `FALSE`. On the other hand, SQL uses three-valued logic (`TRUE`, `FALSE`, and `NULL`) to account for the `NULL` outcome of boolean expressions.

### BETWEEN AND Syntax
The `BETWEEN AND` SQL syntax is a shorthand for an inclusive range filter.<br><br>

```sql
-- filtering for values within a range (inclusive)
SELECT "column" FROM "schema"."table"
WHERE "column" BETWEEN 'value1' AND 'value2';
-- equivalent using comparison operators
SELECT "column" FROM "schema"."table"
WHERE 'value1' <= "column" AND "column" <= 'value2';
```

### IN Keyword
The `IN` operator allows us to check if a value matches any member of a comma-separated list. It serves as a concise shorthand for multiple `OR` conditions.<br><br>

```sql
-- filtering records that match any value in the list
SELECT * FROM "schema"."table"
WHERE "column" IN ('value1', 'value2', 'value3');
-- equivalent using multiple OR conditions
SELECT * FROM "schema"."table"
WHERE "column" = 'value1'
OR "column" = 'value2'
OR "column" = 'value3';
```

### LIKE Keyword
The `LIKE` operator facilitates case-sensitive pattern matching using the `%` wildcard for multiple characters and `_` for a single character. `ILIKE` provides a case-insensitive alternative, which is a feature unique to PostgreSQL. Since these operators are designed for text, we must cast non-string columns to text using the `::text` operator or `CAST()` function to perform matching.<br><br>

```sql
-- case-sensitive pattern matching
SELECT * FROM "schema"."table"
WHERE "column" LIKE 'Ali%';
-- case-insensitive pattern matching
SELECT * FROM "schema"."table"
WHERE "column" ILIKE 'smith';
-- pattern matching with type casting
SELECT * FROM "schema"."table"
WHERE "column"::text LIKE '19._%_';
SELECT * FROM "schema"."table"
WHERE CAST("column" AS text) LIKE '2023%';
```

### Handling Date and Time
Handling date and time is challenging in software engineering because users and data may originate from different time zones. To standardize time across systems, **Universal Time Coordinate (UTC)** is used. UTC is a **time standard**, not a time zone, though it is closely aligned with **Greenwich Mean Time (GMT)**. Modern databases typically store date and time values in UTC and convert them to the user's local time zone when displaying data.<br><br>

```sql
-- displaying database time zone
SHOW timezone;
-- setting database time zone
SET timezone = 'UTC';
-- setting user time zone
ALTER USER "username" SET timezone='UTC';
```

### Datetime Format
- Similar to UTC being a time standard, **ISO-8601** is a time formatting stardard, specifying how datetime should look in computer systems.
- The ISO-8601 format is **YYYY-MM-DDTHH:MM:SS+/-HH:MM**, the last tag being the timezone offset. For example, +02:00 is CEST, and -05:00 is EST.
- Strict adherence to UTC and ISO-8601 ensures interoperability among computer systems.

### Timestamps
- A timestamp is a PostgreSQL data type storing datetime in ISO-8601 format: YYYY-MM-DD HH:MM:SS.MS +/-TZ.
- A timestamp column initialized as `TIMESTAMP WITHOUT TIME ZONE` disregards timezone information and treats the given datetime as UTC.
- A timestamp column initialized as `TIMESTAMP WITH TIME ZONE` converts the given datetime to UTC by offsetting the timezone information.
- We use `DATE` type, if we do not need time info. We use `TIMESTAMP WITHOUT TIME ZONE` type, if we deal with a single timezone. We use `TIMESTAMP WITH TIME ZONE` type, if we deal with multiple timezones.

### Date/Time Operators and Functions
- `NOW()`: Returns the current date and time in `timestamp` type.
- `NOW()::date`: Casts the return value of `NOW()` to `date` type.
- `CURRENT_DATE`: Attribute holding today's date in `date` type.
- `date '1992/11/13'`: Casts the given string to `date` type using ISO-8601 format.
- `TO_CHAR()`: xXx
- `date - date`: Date subtraction returns the difference as number of elapsed days in `integer` type.
- `INTERVAL '10 years 9 months 8 days 7 hours 6 minutes'`: Represents a period of time. Makes it easier to calculate dates and times in the past or ahead of time.
- `AGE()`: Performs subtraction between the given dates and returns the difference in `interval` type.
- `DATE_TRUNC()`: Rounds the given `date` type to the required year | month | day.
- `EXTRACT()`: Returns year | month | day from the given date in `integer` type.
<br><br>

```sql
-- selecting current date and time
SELECT NOW(); --> YYYY-MM-DD HH:MM:SS
-- getting current date
SELECT NOW()::date; --> YYYY-MM-DD
SELECT CURRENT_DATE; --> YYYY-MM-DD
/* formatting date output (see postgres docs)
format pattern: DD/MM/YYYY
format modifiers: D = day, M = month, Y = year, etc... */
SELECT TO_CHAR(CURRENT_DATE, 'DD/MM/YYYY'); --> 01/01/2000
-- subtracting datetime
SELECT NOW() - '1800/01/01';
-- casting to date type
SELECT date '1800/01/01'; --> 1800-01-01
-- calculating age
SELECT AGE(date '1800/01/01'); --> 220 years 4 mons 20 days
SELECT AGE(date '1992/11/13', date '1800/01/01'); --> 192 years 10 mons 12 days
-- extracting date parts
SELECT EXTRACT(YEAR FROM date '1992/11/13'); --> 1992
SELECT EXTRACT(MONTH FROM date '1992/11/13') --> 11
-- rounding dates
SELECT DATE_TRUNC('year', date '1992/11/13'); --> 1992-01-01
SELECT DATE_TRUNC('month', date '1992/11/13'); --> 1992-11-01
-- operating with intervals
SELECT date '1992/11/13' - INTERVAL '5 years 2 months 7 days'; --> 1987-09-06
SELECT date '1992/11/13' + INTERVAL '5 hours 15 minutes'; --> 1992-11-13 05:15:00 
```

### DISTINCT Keyword
- `DISTINCT "column"`: Returns all unique values from the given column.
- `DISTINCT "column1", "column2"`: Returns all unique value combinations from the given columns.<br><br>

```sql
-- selecting unique values from single column
SELECT DISTINCT "column" FROM "schema"."table";
-- selecting unique value combinations from multiple columns
SELECT DISTINCT "column1", "column2" FROM "schema"."table";
```

### Sorting Records
- `GROUP BY`: Sorts records by values from the given column(s) or expression(s).
- `ASC`: Sorts in ascending order. Default when sorting order is not specified.
- `DESC`: Sorts in descending order.
- **Multiple Column Sort:** First sorts by column1, then sorts identical values further by column2.
<br><br>

```sql
-- sorting in ascending order (default)
SELECT * FROM "schema"."table" ORDER BY "column";
-- sorting in descending order
SELECT * FROM "schema"."table" ORDER BY "column" DESC;
-- sorting by expression
SELECT * FROM "schema"."table" ORDER BY LENGTH("column");
-- sorting by multiple columns
SELECT * FROM "schema"."table" ORDER BY "column1", "column2" DESC; -- column1 is ASC
```

### Selecting from Multiple Tables
- **Multi-Table `SELECT`:** A simple way of combining columns from multiple tables.
- **Uncontrolled Permutations:** A simple multi-table `SELECT` returns all possible permiutations of values found in the selected columns.
- **Permutation Filter:** Accepts permutations only with matching primary and foreign keys.
- **Join:** Advanced way of combining columns from two or more tables.
- **Controlled Permutations:** Joins are done with columns that can map/link to one another. The most common approach is to link primary key to foreign key.
<br><br>

```sql
-- multi-table select with permutation filter
SELECT "alias1"."column1", "alias2"."column2"
FROM "schema"."table1" AS "alias1", "schema"."table2" AS "alias2"
WHERE "alias1"."primary" = "alias2"."foreign";
```

### Inner Joins
- **Definition:** An inner join acts like a logical `AND` operator between tables, returning only the records where the specified fields (columns) match in both tables.
- **Multiple Conditions:** Joins can evaluate multiple conditions that are chained with logical operators (`AND`, `OR`, `NOT`).
- **Multiple Tables:** Inner joins can themselves be chained to connect three or more tables.
* **Sorting:** Joins return records in an unsorted, non-deterministic order by default, so an `ORDER BY` clause should always be included.
```sql
-- multiple condition inner join example
SELECT 
    "c"."customer_id", 
    "c"."name", 
    "o"."order_id", 
    "o"."total_amount"
FROM "sales"."customers" AS "c"
INNER JOIN "sales"."orders" AS "o"
    ON "c"."customer_id" = "o"."customer_id"
    AND "o"."status" = 'Completed'
    AND 500.00 <= "o"."total_amount"
ORDER BY "o"."total_amount" DESC;
```

### Self Joins
- **Definition:** A self join is a specific inner join in which a table is joined with **itself**. It is incredibly useful for querying hierarchical data (e.g., finding which employee reports to which manager within the same staff table) or comparing rows within the same table. Because the same table is referenced twice, **aliases must be used** in the query so the database engine can tell them apart.
- **Table Criteria:** For a self join to model relationships (like hierarchies), the table must contain a **unary relationship**. This means the table has a foreign key column (e.g., `manager_id`) that references the primary key column (e.g., `employee_id`) within that very same table.
```sql
-- retrieving employees and their direct managers
SELECT 
    "emp"."employee_id",
    "emp"."name" AS "employee_name",
    "mgr"."name" AS "manager_name"
FROM "staff" AS "emp"
INNER JOIN "staff" AS "mgr" 
    ON "emp"."manager_id" = "mgr"."employee_id";
```

### Outer Joins
- **Outer Joins Overview:** These joins retrieve records that match the specified condition from both tables, as well as non-matching records from one of the tables depending on the direction of the join.
* **Left (Outer) Joins:** This join returns all records from the left (FROM) table, and only those records from the right (JOIN) table that match the specified condition.
* **Left Join Behavior:** If there is no match in the right (JOIN) table for a row in the left (FROM) table, the resulting columns from the right (JOIN) table will contain **NULL** values.
* **Right (Outer) Joins:** This join returns all records from the right (JOIN) table, and only those records from the left (FROM) table that match the specified condision..
* **Right Join Behavior:** If there is no match in the left (FROM) table for a row in the right (JOIN) table, the resulting columns from the left (FROM) table will contain **NULL** values.
* **Key Concept:** Left and Right joins are functionally identical if you swap the table order in your `FROM` and `JOIN` clauses, but Left Joins are much more commonly used in practice for readability.
```sql
-- left join code example
SELECT 
    "customers"."customer_id", 
    "customers"."customer_name", 
    "orders"."order_id"
FROM "customers" -- left table
LEFT JOIN "orders" -- right table
    ON "customers"."customer_id" = "orders"."customer_id";
```

## Resources

<div style="color: navajowhite; font-weight: bold;">

PostgreSQL Aggregate Functions [🔗](https://www.postgresql.org/docs/12/functions-aggregate.html)

Code Commenting Best Practices [🔗](https://www.red-gate.com/simple-talk/databases/oracle-databases/how-to-make-comments-the-most-important-code-you-write/)

PostgreSQL Comparison Operators And Functions [🔗](https://www.postgresql.org/docs/current/functions-comparison.html)

PostgreSQL Operator Precedence [🔗](https://www.postgresql.org/docs/12/sql-syntax-lexical.html#SQL-PRECEDENCE)

PostgreSQL Expression Evaluation Order [🔗](https://www.postgresql.org/docs/12/sql-expressions.html#SYNTAX-EXPRESS-EVAL)

Blog Post About UTC [🔗](https://zachholman.com/talk/utc-is-enough-for-everyone-right)

</div>

## Exercises

<div style="color: navajowhite; font-weight: bold;">



</div>

---
