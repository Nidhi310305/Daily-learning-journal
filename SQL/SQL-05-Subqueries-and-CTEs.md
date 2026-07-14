# 📘 SQL Session 05 – Subqueries & Common Table Expressions (CTEs)

> **Status:** 🚧 In Progress  
> **Track:** Data Analytics & Business Intelligence  
> **Repository:** Daily Learning Journal

---

# 🎯 Learning Objectives

In this session, I aim to understand how SQL queries can be nested inside other queries to solve complex analytical problems. I will also explore Common Table Expressions (CTEs), which improve query readability and modularity.

---

# 📚 Topics to Cover

- What is a Subquery?
- Types of Subqueries
- Scalar Subqueries
- Single-Row Subqueries
- Multi-Row Subqueries
- Correlated Subqueries
- EXISTS
- NOT EXISTS
- ANY
- ALL
- Common Table Expressions (CTEs)
- Recursive CTEs *(Overview)*
- Business Applications
- Interview Questions

---

# 🧠 What is a Subquery?

A subquery is a query written inside another SQL query.

It allows SQL to use the result of one query as the input for another query.

Visualization

```
Outer Query

↓

Inner Query

↓

Result

↓

Final Output
```

---

# Why Use Subqueries?

Subqueries are useful when one query depends on the result of another.

Examples include:

- Finding customers with above-average spending
- Identifying products with maximum sales
- Comparing employees against departmental averages
- Filtering records using calculated values

---

# Types of Subqueries

| Type | Description | Status |
|-------|-------------|--------|
| Scalar Subquery | Returns one value | ⏳ |
| Single Row Subquery | Returns one row | ⏳ |
| Multi Row Subquery | Returns multiple rows | ⏳ |
| Correlated Subquery | Executes once for every outer row | ⏳ |

---

# Scalar Subquery

## Concept

Returns a single value.

Example

```sql
SELECT *
FROM Employees
WHERE Salary >
(
    SELECT AVG(Salary)
    FROM Employees
);
```

Business Question

> Which employees earn above the company average salary?

---

# Multi-Row Subquery

Used when the inner query returns multiple values.

Often combined with:

- IN
- ANY
- ALL

Example

```sql
SELECT *
FROM Products
WHERE Category_ID IN
(
    SELECT Category_ID
    FROM Categories
);
```

---

# Correlated Subquery

A correlated subquery depends on the outer query.

Unlike normal subqueries, it executes once for every row.

Visualization

```
Outer Row 1

↓

Inner Query

↓

Result

-------------------

Outer Row 2

↓

Inner Query

↓

Result
```

---

# EXISTS

Purpose

Checks whether a matching record exists.

Returns TRUE or FALSE.

Example

```sql
SELECT Customer_Name
FROM Customers c
WHERE EXISTS
(
    SELECT 1
    FROM Orders o
    WHERE c.Customer_ID = o.Customer_ID
);
```

Business Question

Which customers have placed at least one order?

---

# NOT EXISTS

Returns rows that have no matching records.

Example

```sql
SELECT Customer_Name
FROM Customers c
WHERE NOT EXISTS
(
    SELECT 1
    FROM Orders o
    WHERE c.Customer_ID = o.Customer_ID
);
```

Business Question

Which customers have never placed an order?

---

# ANY & ALL

These operators compare a value against multiple values returned by a subquery.

Examples

```sql
> ANY
```

```sql
< ALL
```

*(To be explored in detail during future sessions.)*

---

# Common Table Expressions (CTEs)

## Concept

A CTE creates a temporary named result set that exists only for the duration of a query.

Syntax

```sql
WITH SalesSummary AS
(
    SELECT
        Region,
        SUM(Total_Sales) AS Revenue
    FROM Orders
    GROUP BY Region
)

SELECT *
FROM SalesSummary;
```

---

# Why Use CTEs?

CTEs make complex SQL queries:

- Easier to read
- Easier to debug
- Easier to maintain
- More modular

---

# CTE vs Subquery

| Subquery | CTE |
|----------|-----|
| Nested inside query | Defined once using WITH |
| Can become difficult to read | Cleaner and more readable |
| Harder to reuse | Can be referenced multiple times within the same query |

---

# Business Applications

Subqueries and CTEs are commonly used for:

- Customer Segmentation
- Revenue Analysis
- Sales Rankings
- Product Performance
- Inventory Analysis
- Fraud Detection
- Financial Reporting
- Dashboard Preparation

---

# SQL Thinking Framework

Before writing a subquery, ask:

```
Can this problem be solved
using a simple WHERE?

↓

No

↓

Does one query depend on another?

↓

Yes

↓

Use a Subquery
```

---

# Interview Questions

- What is a subquery?
- Difference between Subquery and JOIN?
- What is a correlated subquery?
- Difference between EXISTS and IN?
- When should CTEs be used?
- Advantages of CTEs over nested subqueries?
- Difference between CTE and Temporary Table?

---

# Common Mistakes

❌ Using a subquery when a JOIN is simpler.

---

❌ Forgetting that correlated subqueries execute once per outer row.

---

❌ Returning multiple values in a scalar subquery.

---

❌ Writing deeply nested queries that reduce readability.

---

# Key Takeaways

- Subqueries allow one query to use the result of another query.
- Different subquery types solve different business problems.
- EXISTS checks for matching records efficiently.
- CTEs improve readability and maintainability.
- Complex business reports often combine subqueries, CTEs, and JOINs.

---

# 🚀 Session Progress

| Topic | Status |
|--------|--------|
| Introduction to Subqueries | ⏳ Pending |
| Scalar Subqueries | ⏳ Pending |
| Multi-Row Subqueries | ⏳ Pending |
| Correlated Subqueries | ⏳ Pending |
| EXISTS / NOT EXISTS | ⏳ Pending |
| CTEs | ⏳ Pending |
| Business Problems | ⏳ Pending |
| Interview Questions | ⏳ Pending |

---

# 📈 Learning Outcome

This document will be continuously updated as I progress through advanced SQL topics. By the end of this session, I aim to confidently solve complex business problems using Subqueries and Common Table Expressions while understanding their practical applications in Data Analytics and Business Intelligence.

---

> **Next Session:** SQL Window Functions, Ranking Functions, Analytical Functions, and Advanced Business Reporting.
