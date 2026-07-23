# SQL-05: CASE Statement

## 📖 Overview

The `CASE` statement in SQL is used to create conditional logic inside a query. It works similarly to **IF-ELSE** statements in programming languages and allows us to categorize or transform data based on specified conditions.

Instead of modifying the original data, `CASE` creates a new output column in the query results.

---

## Basic Syntax

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ELSE result3
END
```

---

## Example

```sql
SELECT
    "Order ID",
    "Total Sales",

    CASE
        WHEN "Total Sales" > 1000 THEN 'High Value'
        WHEN "Total Sales" BETWEEN 500 AND 1000 THEN 'Medium Value'
        ELSE 'Low Value'
    END AS Order_Type

FROM Orders;
```

---

## Output Example

| Order ID | Total Sales | Order Type |
|----------|------------:|------------|
| CA-2014-100006 | 261.96 | Low Value |
| CA-2014-100090 | 731.94 | Medium Value |
| CA-2014-100450 | 1540.00 | High Value |

---

## CASE with GROUP BY

```sql
SELECT

CASE
    WHEN "Total Sales" > 1000 THEN 'High Value'
    WHEN "Total Sales" BETWEEN 500 AND 1000 THEN 'Medium Value'
    ELSE 'Low Value'
END AS Order_Type,

COUNT(*) AS Number_of_Orders

FROM Orders

GROUP BY Order_Type;
```

This groups all orders into categories and counts how many orders belong to each category.

---

## CASE Evaluation Order

SQL evaluates `CASE` conditions from **top to bottom**.

Once a condition becomes **TRUE**, SQL stops checking the remaining conditions.

Example:

```sql
CASE
WHEN Sales > 500 THEN 'Medium'
WHEN Sales > 1000 THEN 'High'
END
```

For a sale of **1500**, SQL returns **Medium** because the first condition is already true.

---

## CASE with HAVING

CASE can be combined with aggregate functions and `HAVING` to generate business insights after grouping data.

---

## Business Applications

- Customer Segmentation
- Sales Classification
- Profit Categories
- Risk Analysis
- Performance Ratings
- Order Prioritization

---

## Key Learnings

- CASE works like an IF-ELSE statement.
- It creates a new output column without changing the original data.
- SQL checks CASE conditions from top to bottom.
- CASE can be combined with GROUP BY and HAVING for business analytics.
- Frequently used in reporting and dashboard development.

---

## Interview Questions

### Q1. What is the purpose of CASE in SQL?

It is used to perform conditional logic and return different values based on specified conditions.

---

### Q2. Does CASE modify the table?

No. It only changes the output of the query.

---

### Q3. Can CASE be used with GROUP BY?

Yes. It is commonly used to categorize data before grouping and aggregation.

---

## Progress

- [x] CASE Statement
- [x] Business Classification
- [x] CASE with GROUP BY
- [x] CASE Evaluation Order
- [x] Business Applications

---

**Next Topic:** SQL-06-Subqueries-and-CTEs.md
