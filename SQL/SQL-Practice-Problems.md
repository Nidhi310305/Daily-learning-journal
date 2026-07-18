# 💻 SQL Practice Problems

> **Track:** Data Analytics & Business Intelligence  
> **Repository:** Daily Learning Journal

---

# 🎯 Purpose

This document contains SQL practice problems that I solved while learning SQL. The exercises range from beginner-level concepts to intermediate business analytics queries and are intended to strengthen logical thinking, query-writing skills, and interview preparation.

---

# 📚 Topics Covered

- Filtering
- Aggregate Functions
- GROUP BY & HAVING
- SQL JOINs
- UNION
- Business Queries
- Subqueries *(Upcoming)*
- Window Functions *(Upcoming)*

---

# 🟢 Beginner Level

## Problem 1 — Count Total Employees

**Question**

Return the total number of employees.

### Solution

```sql
SELECT COUNT(*)
FROM Employees;
```

### Concepts

- COUNT()

---

## Problem 2 — Total Sales

**Question**

Calculate the total sales.

### Solution

```sql
SELECT SUM(Total_Sales)
FROM Orders;
```

### Concepts

- SUM()

---

## Problem 3 — Average Salary

**Question**

Find the average salary of employees.

### Solution

```sql
SELECT AVG(Salary)
FROM Employees;
```

### Concepts

- AVG()

---

## Problem 4 — Minimum & Maximum Price

**Question**

Find the cheapest and most expensive product.

### Solution

```sql
SELECT
MIN(Price),
MAX(Price)
FROM Products;
```

### Concepts

- MIN()
- MAX()

---

# 🟡 Intermediate Level

## Problem 5 — Sales by Region

**Question**

Calculate total sales for each region.

### Solution

```sql
SELECT
Region,
SUM(Total_Sales)
FROM Orders
GROUP BY Region;
```

### Concepts

- GROUP BY
- SUM()

---

## Problem 6 — Average Salary by Department

**Question**

Display departments where the average salary exceeds ₹80,000.

### Solution

```sql
SELECT
Department,
AVG(Salary)
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > 80000;
```

### Concepts

- GROUP BY
- HAVING

---

## Problem 7 — Employees in Selected Departments

**Question**

Show employees from HR, Finance, and Sales.

### Solution

```sql
SELECT *
FROM Employees
WHERE Department IN
('HR','Finance','Sales');
```

### Concepts

- IN

---

## Problem 8 — Products Within Price Range

**Question**

Display products priced between ₹1000 and ₹40000.

### Solution

```sql
SELECT *
FROM Products
WHERE Price BETWEEN 1000 AND 40000;
```

### Concepts

- BETWEEN

---

## Problem 9 — Top 5 Selling Products

**Question**

Retrieve the top five products by sales.

### Solution

```sql
SELECT *
FROM Products
ORDER BY Sales DESC
LIMIT 5;
```

### Concepts

- ORDER BY
- LIMIT

---

# 🟠 JOIN Practice

## Problem 10 — Customer Orders

**Question**

Display customer names along with their order amounts.

### Solution

```sql
SELECT
c.Customer_Name,
o.Total_Sales
FROM Customers c
INNER JOIN Orders o
ON c.Customer_ID = o.Customer_ID;
```

### Concepts

- INNER JOIN

---

## Problem 11 — Customers Without Orders

**Question**

Display all customers, even if they have never placed an order.

### Solution

```sql
SELECT
c.Customer_Name,
o.Total_Sales
FROM Customers c
LEFT JOIN Orders o
ON c.Customer_ID = o.Customer_ID;
```

### Concepts

- LEFT JOIN

---

## Problem 12 — Employee & Manager

**Question**

Display employees with their managers.

### Solution

```sql
SELECT
e.Employee_Name,
m.Employee_Name AS Manager
FROM Employees e
JOIN Employees m
ON e.Manager_ID = m.Employee_ID;
```

### Concepts

- SELF JOIN

---

## Problem 13 — Product & Store Combinations

**Question**

Generate every product-store combination.

### Solution

```sql
SELECT *
FROM Products
CROSS JOIN Stores;
```

### Concepts

- CROSS JOIN

---

# 🔵 Business Analytics Practice

## Problem 14 — Total Sales by Region

```sql
SELECT
Region,
SUM(Total_Sales)
FROM Orders
GROUP BY Region;
```

---

## Problem 15 — Profit Margin by Category

```sql
SELECT
Category,
ROUND(
SUM(Profit) /
SUM(Total_Sales) * 100,
2
) AS Profit_Margin
FROM Orders
GROUP BY Category;
```

---

## Problem 16 — Top Customers by Revenue

```sql
SELECT
Customer_Name,
SUM(Total_Sales)
FROM Orders
GROUP BY Customer_Name
ORDER BY SUM(Total_Sales) DESC
LIMIT 5;
```

---

## Problem 17 — Monthly Sales Trend

```sql
SELECT
SUBSTR(Order_Date,4,2) AS Month,
SUM(Total_Sales)
FROM Orders
GROUP BY Month
ORDER BY CAST(Month AS INTEGER);
```

---

# 🔴 Interview Challenge Questions

### ✔ Difference between WHERE and HAVING?

---

### ✔ Difference between COUNT(*) and COUNT(column)?

---

### ✔ Difference between INNER JOIN and LEFT JOIN?

---

### ✔ Difference between UNION and UNION ALL?

---

### ✔ Why is GROUP BY necessary?

---

### ✔ Why do we use ORDER BY before LIMIT?

---

### ✔ Difference between LIKE and REGEXP?

---

### ✔ Difference between RANK() and DENSE_RANK? *(Upcoming)*

---

### ✔ Difference between JOIN and Subquery? *(Upcoming)*

---

# 📈 Difficulty Progress

| Level | Status |
|--------|--------|
| SQL Basics | ✅ Completed |
| Aggregate Functions | ✅ Completed |
| GROUP BY | ✅ Completed |
| HAVING | ✅ Completed |
| JOINs | ✅ Completed |
| Advanced Filtering | ✅ Completed |
| UNION | ✅ Completed |
| Business Queries | ✅ Completed |
| Subqueries | ⏳ Upcoming |
| Window Functions | ⏳ Upcoming |

---

# 🎯 Learning Outcome

By solving these practice problems, I strengthened my understanding of SQL syntax, analytical thinking, and business-oriented problem solving. Each exercise helped reinforce core SQL concepts while improving my ability to translate business requirements into efficient SQL queries.

---

> **Note:** This file will continue to grow as I solve more SQL problems and interview questions throughout my learning journey.
