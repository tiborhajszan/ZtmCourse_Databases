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

### SQL Command Categories
SQL commands are organized into functional groups including
- **DCL** (Data Control Language) for managing permissions,
- **DDL** (Data Definition Language) for defining structures,
- **DML** (Data Manipulation Language) for modifying records,
- **DQL** (Data Query Language) for fetching data.

### Data Retrieval
- **Role of DQL:** The Data Query Language is centered around the `SELECT` statement, which is the most frequently used command in SQL.
- **Purpose of `SELECT`:** The primary purpose of the `SELECT` statement is to retrieve data from a database without changing the underlying data.

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
- **Aggregate Functions:** Combine multiple records (e.g., all values in a column) and return a single aggregated value (e.g., `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`).
- **Scalar Functions:** Like the `map()` function in Python, they operate on each record individually and return multiple corresponding values (e.g., `CONCAT()`, `LENGTH()`, `UPPER()`).

### CONCAT() Function
```sql
-- concatenating columns
SELECT CONCAT("column1", ' ', "column2") AS "concatenated_column" FROM "schema"."table";
```

### Aggregate Functions
```sql
-- calculating the sum of a set of values
SELECT SUM("column") FROM "schema"."table";
-- counting the total number of records in a column
SELECT COUNT("column") FROM "schema"."table";
-- calculating the average of a set of values
SELECT AVG("column") FROM "schema"."table";
-- finding the minimum value in a set of values
SELECT MIN("column") FROM "schema"."table";
-- finding the maximum value in a set of values
SELECT MAX("column") FROM "schema"."table";
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
  - Be **careful and defensive:** Allow `NULL` values only where it is absolutely essential. Always check for and filter out `NULL` values in your queries.
  - Be **mindful and rational:** Consider the consequences of allowing `NULL` values. For example, do not allow `NULL` values for columns that are used in calculations or contain required business information. But you can allow `NULL` values for columns that are optional or have default values.
  - Be **deliberate:** Make conscious decisions about `NULL` values and communicate them clearly to your team.
- ⚠️ <span style="color: #FF6B6B;">**Danger:**</span> `NULL` is dangerous because whatever operation you perform with `NULL`, the result will always be `NULL`, which may cause all sorts of issues in your applications.

### IS Keyword
The `IS` keyword is a special comparison operator that allows us to check for `NULL`, `TRUE`, or `FALSE` values, because the `=` operator cannot be used here. The `IS NOT` keyword is the opposite of the `IS` keyword. As a result, `IS NOT TRUE` is equivalent to `IS FALSE`, and `IS NOT FALSE` is equivalent to `IS TRUE`.<br><br>

```sql
-- checking for NULL values
SELECT * FROM "schema"."table" WHERE "column" IS NULL;
-- checking for TRUE values
SELECT * FROM "schema"."table" WHERE "boolean_column" IS NOT TRUE;
-- checking for FALSE values
SELECT * FROM "schema"."table" WHERE "boolean_column" IS FALSE;
```

### NULL Coalescing
When working with datasets that may contain `NULL`, we should substitute `NULL` values with a default value using the `COALESCE()` function. The `COALESCE()` function returns the first non-`NULL` value from the list of its arguments.<br><br>

```sql
-- returning the first non-NULL value
SELECT COALESCE("column1", "column2", 'default_value') AS "result" FROM "schema"."table";
```

## Resources

<div style="color: navajowhite; font-weight: bold;">

PostgreSQL Aggregate Functions [🔗](https://www.postgresql.org/docs/12/functions-aggregate.html)

Code Commenting Best Practices [🔗](https://www.red-gate.com/simple-talk/databases/oracle-databases/how-to-make-comments-the-most-important-code-you-write/)

PostgreSQL Comparison Operators And Functions [🔗](https://www.postgresql.org/docs/current/functions-comparison.html)

PostgreSQL Operator Precedence [🔗](https://www.postgresql.org/docs/12/sql-syntax-lexical.html#SQL-PRECEDENCE)

PostgreSQL Expression Evaluation Order [🔗](https://www.postgresql.org/docs/12/sql-expressions.html#SYNTAX-EXPRESS-EVAL)

</div>

## Exercises

<div style="color: navajowhite; font-weight: bold;">

Aggregate Functions
- Questions [🔗](https://github.com/mobinni/Complete-SQL-Database-Bootcamp-Zero-to-Mastery/blob/master/SQL%20Deep%20Dive/Aggregate%20Functions/exercises.sql)
- Answers [🔗](https://github.com/mobinni/Complete-SQL-Database-Bootcamp-Zero-to-Mastery/blob/master/SQL%20Deep%20Dive/Aggregate%20Functions/answers.sql)

WHERE Clause
- W3Schools Exercise [🔗](https://www.w3schools.com/sql/exercise.asp?x=xrcise_where1)

Comparison Operators
- Questions [🔗](https://github.com/mobinni/Complete-SQL-Database-Bootcamp-Zero-to-Mastery/blob/master/SQL%20Deep%20Dive/Comparison%20Operators/questions.sql)
- Answers [🔗](https://github.com/mobinni/Complete-SQL-Database-Bootcamp-Zero-to-Mastery/blob/master/SQL%20Deep%20Dive/Comparison%20Operators/answers.sql)
- DB Fiddle [🔗](https://www.db-fiddle.com/f/upmzr6GdKYgJew2aXNrLpE/0)

Operator Precedence
- Questions [🔗](https://github.com/mobinni/Complete-SQL-Database-Bootcamp-Zero-to-Mastery/blob/master/SQL%20Deep%20Dive/Operator%20precendence/questions.sql)
- Answers [🔗](https://github.com/mobinni/Complete-SQL-Database-Bootcamp-Zero-to-Mastery/blob/master/SQL%20Deep%20Dive/Operator%20precendence/answers.sql)

NULL Coalescing
- Questions [🔗](https://github.com/mobinni/Complete-SQL-Database-Bootcamp-Zero-to-Mastery/blob/master/SQL%20Deep%20Dive/Null%20Values/questions.sql)
- Answers [🔗](https://github.com/mobinni/Complete-SQL-Database-Bootcamp-Zero-to-Mastery/blob/master/SQL%20Deep%20Dive/Null%20Values/answers.sql)
- DB Fiddle [🔗](https://www.db-fiddle.com/f/PnGNcaPYfGoEDvfexzEUA/0)

</div>

---
