# 📘 SQL Session 02 – SQL JOINs & Relational Databases

> **Date:** 06 July 2026  
> **Track:** Data Analytics & Business Intelligence  
> **Repository:** Daily Learning Journal

---

# 🎯 Learning Objectives

In this session, I learned how relational databases connect information stored across multiple tables using SQL JOINs. I practiced writing JOIN queries, identifying join keys, and solving business-oriented problems involving multiple related tables.

---

# 📚 Topics Covered

- Relational Databases
- Primary Key & Foreign Key
- JOIN Keys
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- FULL OUTER JOIN
- Multi-table JOINs
- Bridge Tables
- SQL Aliases
- Business Query Interpretation

---

# 🧠 Why Do We Need JOINs?

In relational databases, data is stored in multiple tables to reduce duplication.

Example

### Customers Table

| Customer ID | Customer Name |
|------------:|---------------|
|101|Alice|
|102|Bob|

---

### Orders Table

| Order ID | Customer ID | Total Sales |
|---------:|------------:|------------:|
|1|101|500|
|2|102|700|
|3|101|300|

Notice:

- Customer name exists in **Customers**
- Sales exist in **Orders**

To display

```
Customer Name + Sales
```

we need a JOIN.

---

# 🔑 Join Key

A Join Key is the common column shared between two tables.

Example

```
Customers.Customer_ID

↓

Orders.Customer_ID
```

This relationship allows SQL to connect both tables.

---

# 🧩 INNER JOIN

## Purpose

Returns only matching rows from both tables.

---

### Visualization

```
Customers

Alice
Bob
Emma

        ∩

Orders

Alice
Bob

↓

Result

Alice
Bob
```

Only matching records appear.

---

### Syntax

```sql
SELECT
c.Customer_Name,
o.Total_Sales
FROM Customers c
INNER JOIN Orders o
ON c.Customer_ID = o.Customer_ID;
```

---

### Business Example

Display

- Customer Name
- Order Amount

---

# 🧩 LEFT JOIN

## Purpose

Keeps every row from the left table.

If no matching record exists in the right table,

SQL returns NULL.

---

Visualization

```
LEFT TABLE

Alice
Bob
Emma

↓

Keep Everything

↓

Orders

Alice ✔

Bob ✔

Emma NULL
```

---

Example

| Customer | Sales |
|-----------|------:|
|Alice|500|
|Bob|700|
|Emma|NULL|

---

### Syntax

```sql
SELECT
c.Customer_Name,
o.Total_Sales
FROM Customers c
LEFT JOIN Orders o
ON c.Customer_ID=o.Customer_ID;
```

---

# 🧩 RIGHT JOIN

## Purpose

Keeps every row from the right table.

Missing matches become NULL on the left side.

---

Visualization

```
Orders

500
700
300

↓

Keep Everything

↓

Customer

Alice
Bob
NULL
```

---

# 🧩 FULL OUTER JOIN

## Purpose

Keeps every row from both tables.

Missing matches become NULL.

---

Visualization

```
LEFT TABLE

Alice
Bob
Emma

+

RIGHT TABLE

Alice
Bob
Finance

↓

Result

Alice

Bob

Emma

Finance
```

---

# 🧩 JOIN Comparison

| JOIN | Keeps |
|-------|-------|
|INNER|Only matching rows|
|LEFT|Everything from Left Table|
|RIGHT|Everything from Right Table|
|FULL OUTER|Everything from Both Tables|

---

# 🧠 SQL Execution During JOIN

SQL processes JOIN queries logically.

```
FROM

↓

JOIN

↓

ON

↓

WHERE

↓

GROUP BY

↓

HAVING

↓

SELECT

↓

ORDER BY
```

---

# 🧩 Multi-table JOINs

Some business problems require joining more than two tables.

Example

```
Customers

↓

Orders

↓

Order_Items

↓

Products
```

---

Business Question

> Show Customer Name and Product Name ordered.

Relationship

```
Customers

↓

Customer_ID

↓

Orders

↓

Order_ID

↓

Order_Items

↓

Product_ID

↓

Products
```

---

Example Query

```sql
SELECT
c.Customer_Name,
p.Product_Name

FROM Customers c

JOIN Orders o
ON c.Customer_ID=o.Customer_ID

JOIN Order_Items oi
ON o.Order_ID=oi.Order_ID

JOIN Products p
ON oi.Product_ID=p.Product_ID;
```

---

# 🌉 Bridge Tables

Sometimes two tables cannot be joined directly.

Example

Movies

↓

Casting

↓

Actors

Movie

```
Movie_ID
```

Actor

```
Actor_ID
```

No common key exists.

Casting becomes the bridge.

```
Movie

↓

Casting

↓

Actor
```

---

# 🏷 SQL Aliases

Aliases make queries easier to read.

Instead of

```sql
Customers.Customer_Name
```

Use

```sql
c.Customer_Name
```

Example

```sql
FROM Customers c
JOIN Orders o
```

---

# 💻 Practice Queries

## Customer Name & Sales

```sql
SELECT
c.Customer_Name,
o.Total_Sales
FROM Customers c
INNER JOIN Orders o
ON c.Customer_ID=o.Customer_ID;
```

---

## Customer with Ordered Products

```sql
SELECT
c.Customer_Name,
p.Product_Name
FROM Customers c
JOIN Orders o
ON c.Customer_ID=o.Customer_ID
JOIN Order_Items oi
ON o.Order_ID=oi.Order_ID
JOIN Products p
ON oi.Product_ID=p.Product_ID;
```

---

# 💼 Business Applications

JOINs are used in almost every business dashboard.

Examples

- Customer Purchase History
- Product Performance
- Sales by Region
- Employee Department Reports
- Order Tracking
- Inventory Management
- Banking Transactions
- E-commerce Analytics

---

# ⚠ Common Mistakes

❌ Joining on the wrong column.

Always identify the correct Join Key.

---

❌ Forgetting the ON condition.

```sql
JOIN Orders
```

Incorrect.

Always specify

```sql
ON Customers.Customer_ID = Orders.Customer_ID
```

---

❌ Selecting columns from the wrong table.

Always check which table contains the required information.

---

# 🧠 Interview Tips

Before writing any JOIN query, ask yourself:

### 1️⃣ What information do I need?

Example

```
Customer Name

+

Order Amount
```

---

### 2️⃣ Which tables contain this information?

```
Customer Name

↓

Customers

----------------

Order Amount

↓

Orders
```

---

### 3️⃣ What is the Join Key?

```
Customer_ID
```

---

### 4️⃣ Which JOIN should I use?

Need only matching rows?

→ INNER JOIN

Need all customers?

→ LEFT JOIN

Need all orders?

→ RIGHT JOIN

Need everything?

→ FULL OUTER JOIN

---

# 📝 Key Takeaways

- Relational databases store data across multiple related tables.
- JOINs combine related information.
- INNER JOIN returns matching rows only.
- LEFT JOIN keeps all rows from the left table.
- RIGHT JOIN keeps all rows from the right table.
- FULL OUTER JOIN keeps every row from both tables.
- Multi-table JOINs solve complex business problems.
- Bridge tables connect unrelated tables.
- Aliases improve query readability.

---

# 🚀 Session Summary

✅ Understood Relational Databases

✅ Learned Join Keys

✅ Practiced INNER JOIN

✅ Practiced LEFT JOIN

✅ Practiced RIGHT JOIN

✅ Learned FULL OUTER JOIN

✅ Solved Multi-table JOIN Problems

✅ Understood Bridge Tables

✅ Learned SQL Aliases

✅ Solved Business-Oriented JOIN Queries

---

> **Next Session:** Advanced SQL — SELF JOIN, NATURAL JOIN, CROSS JOIN, UNION, Advanced Filtering, String Functions, and Business Analytics Queries.
