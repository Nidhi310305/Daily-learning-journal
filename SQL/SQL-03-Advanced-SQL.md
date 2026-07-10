# 📘 SQL Session 03 – Advanced SQL

> **Date:** 07 July 2026  
> **Track:** Data Analytics & Business Intelligence  
> **Repository:** Daily Learning Journal

---

# 🎯 Learning Objectives

In this session, I explored advanced SQL concepts frequently used in Data Analytics and Business Intelligence. The focus was on advanced filtering, different JOIN variations, combining query results, string manipulation, and data type conversion while understanding their practical business applications.

---

# 📚 Topics Covered

- IN
- BETWEEN
- NOT BETWEEN
- LIMIT
- LIKE vs REGEXP
- SELF JOIN
- NATURAL JOIN
- CROSS JOIN
- UNION
- UNION ALL
- SUBSTR()
- CAST()

---

# 🔍 Advanced Filtering

## IN Operator

### Purpose

Used to filter multiple specific values without writing multiple OR conditions.

### Syntax

```sql
SELECT *
FROM Employees
WHERE Department IN ('HR', 'Finance', 'Sales');
```

Equivalent to

```sql
WHERE Department='HR'
OR Department='Finance'
OR Department='Sales';
```

### Business Use Cases

- Filter selected departments
- Selected cities
- Selected customer segments

---

## BETWEEN

### Purpose

Filters values within a continuous range.

### Syntax

```sql
SELECT *
FROM Products
WHERE Price BETWEEN 1000 AND 40000;
```

Equivalent to

```sql
Price >= 1000
AND Price <= 40000
```

### Important

BETWEEN is **inclusive**.

```
1000 ✔

40000 ✔
```

---

## NOT BETWEEN

Returns values outside the specified range.

```sql
SELECT *
FROM Products
WHERE Price NOT BETWEEN 1000 AND 40000;
```

---

# 📊 LIMIT

## Purpose

Returns only the first N rows.

```sql
SELECT *
FROM Sales
LIMIT 5;
```

---

## Top N Records

To retrieve the highest values:

```sql
SELECT *
FROM Sales
ORDER BY Total_Sales DESC
LIMIT 5;
```

### Why ORDER BY First?

Without sorting, LIMIT simply returns the first rows stored in the database.

---

# 🔤 LIKE vs REGEXP

## LIKE

Best for simple pattern matching.

Example

```sql
SELECT *
FROM Products
WHERE Product_Name LIKE '%Pro%';
```

---

## REGEXP

Used for advanced text matching.

Suitable when multiple patterns or complex conditions are required.

---

# 🔄 SELF JOIN

## Concept

A SELF JOIN joins a table with itself.

Useful when two related entities exist in the same table.

Example:

Employees

| Employee | Manager_ID |
|-----------|------------|
| Alice | 2 |
| Bob | 3 |
| Emma | NULL |

Result

| Employee | Manager |
|-----------|----------|
| Alice | Bob |
| Bob | Emma |

---

### Syntax

```sql
SELECT
e.Employee_Name,
m.Employee_Name AS Manager
FROM Employees e
JOIN Employees m
ON e.Manager_ID = m.Employee_ID;
```

---

### Business Applications

- Employee → Manager
- Category → Parent Category
- Organizational hierarchy

---

# 🌿 NATURAL JOIN

## Concept

Automatically joins tables using columns with identical names.

Example

```sql
SELECT *
FROM Students
NATURAL JOIN Courses;
```

---

### Advantages

- Shorter syntax
- No ON clause required

---

### Risks

If additional columns share the same name, SQL will attempt to join on all of them.

This may produce unexpected results.

**Best Practice**

Prefer explicit JOINs.

```sql
INNER JOIN
...
ON ...
```

---

# ✖ CROSS JOIN

## Concept

Returns every possible combination of rows.

Visualization

```
Table A

2 Rows

×

Table B

3 Rows

↓

6 Rows
```

---

### Formula

```
Rows in A × Rows in B
```

---

### Example

```sql
SELECT *
FROM Products
CROSS JOIN Stores;
```

---

### Business Applications

- Product × Store combinations
- Scenario generation
- Planning reports

---

# 🔗 UNION

## Purpose

Stacks rows from multiple SELECT statements.

Example

Table A

```
Delhi
Mumbai
Pune
```

Table B

```
Mumbai
Chennai
```

Result

```
Delhi
Mumbai
Pune
Chennai
```

Duplicate rows are removed.

---

## UNION ALL

Same as UNION but keeps duplicate rows.

Result

```
Delhi
Mumbai
Pune
Mumbai
Chennai
```

---

## JOIN vs UNION

| JOIN | UNION |
|------|--------|
| Combines Columns | Combines Rows |
| Requires relationship | No relationship |
| Uses ON | No ON |
| Horizontal Combination | Vertical Combination |

---

# ✂ String Functions

## SUBSTR()

Extracts part of a string.

### Syntax

```sql
SUBSTR(column,start,length)
```

---

### Example

Date

```
05-12-2025
```

Query

```sql
SUBSTR(Order_Date,4,2)
```

Result

```
12
```

The extracted value represents the month.

---

### Business Applications

- Extract Month
- Extract Year
- Product Codes
- Customer IDs

---

# 🔄 CAST()

## Purpose

Converts one data type into another.

Example

```sql
CAST(Month AS INTEGER)
```

---

### Why Use CAST?

Without CAST

```
1

10

11

2
```

(Text Sorting)

With CAST

```
1

2

10

11
```

(Numeric Sorting)

---

### Business Applications

- Date Analysis
- Numeric Sorting
- Data Cleaning
- Report Generation

---

# 💻 Practice Queries

### Filter Multiple Departments

```sql
SELECT *
FROM Employees
WHERE Department IN ('HR','Finance');
```

---

### Products Within Price Range

```sql
SELECT *
FROM Products
WHERE Price BETWEEN 1000 AND 40000;
```

---

### Top Five Products

```sql
SELECT *
FROM Products
ORDER BY Sales DESC
LIMIT 5;
```

---

### SELF JOIN

```sql
SELECT
e.Employee_Name,
m.Employee_Name AS Manager
FROM Employees e
JOIN Employees m
ON e.Manager_ID = m.Employee_ID;
```

---

### CROSS JOIN

```sql
SELECT *
FROM Products
CROSS JOIN Stores;
```

---

### UNION

```sql
SELECT City
FROM Branch_A

UNION

SELECT City
FROM Branch_B;
```

---

# 💼 Business Applications

These SQL concepts are widely used in analytical dashboards.

Examples include:

- Top Selling Products
- Sales Leaderboards
- Monthly Reports
- Organizational Hierarchies
- Customer Segmentation
- Marketing Analysis
- Product Availability
- Inventory Planning

---

# ⚠ Common Mistakes

❌ Using LIMIT without ORDER BY.

---

❌ Using NATURAL JOIN on production databases.

---

❌ Confusing UNION with JOIN.

---

❌ Forgetting that UNION removes duplicates.

---

❌ Forgetting that SUBSTR() returns text.

Use CAST() whenever numeric sorting is required.

---

# 🧠 Interview Tips

Before writing a query, ask yourself:

### Do I need to...

✔ Filter?

→ WHERE

✔ Filter multiple values?

→ IN

✔ Filter a range?

→ BETWEEN

✔ Limit results?

→ LIMIT

✔ Match records?

→ JOIN

✔ Combine result sets?

→ UNION

✔ Extract text?

→ SUBSTR()

✔ Convert datatype?

→ CAST()

---

# 📝 Key Takeaways

- IN simplifies multiple OR conditions.
- BETWEEN works on continuous ranges.
- LIMIT should usually be paired with ORDER BY.
- SELF JOIN relates records within the same table.
- NATURAL JOIN automatically matches common columns.
- CROSS JOIN generates every possible combination.
- UNION removes duplicates.
- UNION ALL preserves duplicates.
- SUBSTR() extracts part of a string.
- CAST() converts one data type into another.

---

# 🚀 Session Summary

✅ Advanced Filtering

✅ Advanced JOIN Types

✅ UNION & UNION ALL

✅ String Functions

✅ Data Type Conversion

✅ Business-Oriented SQL Thinking

---

> **Next Session:** Business Analytics SQL Queries, Real-world Reporting, Customer Segmentation, Revenue Analysis, Profitability Metrics, and Dashboard-Oriented SQL.
