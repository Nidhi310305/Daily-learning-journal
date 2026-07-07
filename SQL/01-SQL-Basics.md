# 📘 SQL Session 01 – SQL Fundamentals

> **Date:** 05 July 2026  
> **Track:** Data Analytics & Business Intelligence  
> **Repository:** Daily Learning Journal

---

# 🎯 Learning Objectives

In this session, I learned the core SQL concepts required to retrieve, filter, and summarize data from relational databases. The focus was on understanding how SQL answers business questions using aggregate functions and grouped analysis.

---

# 📚 Topics Covered

- Introduction to SQL Queries
- SELECT Statement
- Aggregate Functions
  - COUNT()
  - SUM()
  - AVG()
  - MIN()
  - MAX()
- COUNT(column) vs COUNT(*)
- GROUP BY
- HAVING
- WHERE vs HAVING
- SQL Query Execution Flow

---

# 🧠 Key Concepts

## 1️⃣ SELECT

Used to retrieve data from a table.

### Syntax

```sql
SELECT column_name
FROM table_name;
```

### Example

```sql
SELECT Name
FROM Customers;
```

---

## 2️⃣ Aggregate Functions

Aggregate functions summarize multiple rows into a single value.

| Function | Purpose |
|----------|---------|
| COUNT() | Counts records |
| SUM() | Calculates total |
| AVG() | Calculates average |
| MIN() | Returns smallest value |
| MAX() | Returns largest value |

---

## COUNT()

Counts the number of non-null values.

### Example

```sql
SELECT COUNT(Population)
FROM World;
```

### Example Table

| Population |
|-----------:|
|100|
|200|
|NULL|
|300|

Result

```
3
```

Only non-null values are counted.

---

## COUNT(*)

Counts every row.

```sql
SELECT COUNT(*)
FROM World;
```

Same table

| Population |
|-----------:|
|100|
|200|
|NULL|
|300|

Result

```
4
```

All rows are counted.

---

## SUM()

Calculates the total of a numeric column.

```sql
SELECT SUM(Population)
FROM World;
```

Example

```
100 + 200 + 300 = 600
```

---

## AVG()

Returns the average of all non-null values.

```sql
SELECT AVG(Population)
FROM World;
```

Example

```
(100 + 200 + 300)

÷

3

=

200
```

NULL values are ignored.

---

## MIN()

Returns the smallest value.

```sql
SELECT MIN(Population)
FROM World;
```

---

## MAX()

Returns the largest value.

```sql
SELECT MAX(Population)
FROM World;
```

---

# 📦 GROUP BY

## Purpose

Groups rows having the same value before applying aggregate functions.

---

### Example

| Continent | Population |
|-----------|-----------:|
|Asia|1400|
|Asia|1500|
|Europe|80|
|Europe|70|

Query

```sql
SELECT
    Continent,
    SUM(Population)
FROM World
GROUP BY Continent;
```

Result

| Continent | Total Population |
|-----------|-----------------:|
|Asia|2900|
|Europe|150|

---

## Visualization

```
Asia

1400
1500

↓

SUM

↓

2900

---------------------

Europe

80
70

↓

SUM

↓

150
```

---

# ⭐ Golden Rule of GROUP BY

Every column in the SELECT statement must be either:

- Included in the GROUP BY clause
- OR used inside an aggregate function

Correct

```sql
SELECT
Department,
AVG(Salary)
FROM Employees
GROUP BY Department;
```

Incorrect

```sql
SELECT
Department,
Salary
FROM Employees
GROUP BY Department;
```

Reason:

`Salary` is neither grouped nor aggregated.

---

# 🔍 WHERE vs HAVING

## WHERE

Filters rows **before** grouping.

```sql
SELECT *
FROM Employees
WHERE Department='HR';
```

---

## HAVING

Filters groups **after** aggregation.

```sql
SELECT
Department,
AVG(Salary)
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > 80000;
```

---

## Memory Trick

```
WHERE

↓

Rows

-------------------

GROUP BY

↓

Groups

-------------------

HAVING

↓

Filter Groups
```

---

# ⚙ SQL Execution Flow

Although we write SQL in one order, SQL processes it differently.

```
FROM

↓

WHERE

↓

GROUP BY

↓

Aggregate Functions

↓

HAVING

↓

SELECT

↓

ORDER BY
```

Understanding this execution order helps explain why aggregate functions cannot be used inside the WHERE clause.

---

# 💻 Practice Queries

### Total Population

```sql
SELECT SUM(Population)
FROM World;
```

---

### Number of Countries

```sql
SELECT COUNT(*)
FROM World;
```

---

### Average Population

```sql
SELECT AVG(Population)
FROM World;
```

---

### Population by Continent

```sql
SELECT
Continent,
SUM(Population)
FROM World
GROUP BY Continent;
```

---

### Departments with Average Salary Greater Than 80000

```sql
SELECT
Department,
AVG(Salary)
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > 80000;
```

---

# 💼 Business Applications

These SQL concepts are widely used in Business Intelligence and Data Analytics.

Examples include:

- Total Sales by Region
- Average Salary by Department
- Customer Count
- Monthly Revenue
- Product Performance
- Sales Summary Reports

---

# ⚠ Common Mistakes

❌ Using aggregate functions inside `WHERE`

```sql
WHERE AVG(Salary) > 80000
```

✅ Correct

```sql
HAVING AVG(Salary) > 80000
```

---

❌ Selecting columns that are neither grouped nor aggregated.

Always follow the GROUP BY Golden Rule.

---

# 🧠 Key Takeaways

- Aggregate functions summarize data.
- COUNT(column) ignores NULL values.
- COUNT(*) counts every row.
- GROUP BY creates groups before aggregation.
- HAVING filters aggregated results.
- WHERE filters rows before grouping.
- SQL follows a logical execution order that differs from the written query.

---

# 🚀 Session Summary

✅ Learned SQL Fundamentals

✅ Practiced Aggregate Functions

✅ Understood GROUP BY

✅ Learned WHERE vs HAVING

✅ Explored SQL Execution Order

✅ Solved Business-Oriented SQL Aggregation Problems

---

> **Next Session:** SQL JOINs, Relational Databases, and Multi-table Queries.
