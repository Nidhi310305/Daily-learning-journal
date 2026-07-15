# 📘 SQL Session 06 – Window Functions

> **Status:** 🚧 In Progress  
> **Track:** Data Analytics & Business Intelligence  
> **Repository:** Daily Learning Journal

---

# 🎯 Learning Objectives

In this session, I will learn how SQL Window Functions perform calculations across related rows without collapsing the dataset. Unlike GROUP BY, Window Functions preserve every row while providing analytical insights such as ranking, running totals, moving averages, and comparisons.

---

# 📚 Topics to Cover

- What are Window Functions?
- OVER() Clause
- PARTITION BY
- ORDER BY in Window Functions
- ROW_NUMBER()
- RANK()
- DENSE_RANK()
- NTILE()
- LAG()
- LEAD()
- FIRST_VALUE()
- LAST_VALUE()
- Running Totals
- Moving Averages
- Window Aggregates
- Business Applications
- Interview Questions

---

# 🧠 What are Window Functions?

Window Functions perform calculations across a set of rows while preserving each individual row.

Unlike GROUP BY, they **do not reduce the number of rows**.

---

## Visualization

Without Window Functions

```
Sales

↓

GROUP BY

↓

One Row Per Group
```

---

With Window Functions

```
Sales

↓

Window Function

↓

Every Row Remains

+

Additional Calculation
```

---

# Why Window Functions?

Useful when you need calculations without losing row-level information.

Examples include:

- Sales Ranking
- Running Totals
- Previous Month Comparison
- Customer Ranking
- Profit Trends
- Year-over-Year Growth
- Leaderboards

---

# OVER() Clause

Every Window Function requires an OVER() clause.

General Syntax

```sql
FUNCTION(column)
OVER(...)
```

The OVER() clause defines the window on which the function operates.

---

# PARTITION BY

Creates logical groups while keeping all rows.

Example

```sql
SUM(Sales)
OVER(PARTITION BY Region)
```

Each region is calculated independently.

---

# ORDER BY inside OVER()

Defines the calculation order within each partition.

Example

```sql
SUM(Sales)
OVER(
PARTITION BY Region
ORDER BY Order_Date
)
```

Useful for running totals.

---

# ROW_NUMBER()

Assigns a unique sequential number.

Example

```sql
ROW_NUMBER()
OVER(
ORDER BY Sales DESC
)
```

Example Output

| Customer | Sales | Row Number |
|----------|------:|-----------:|
| Alice | 900 | 1 |
| Bob | 850 | 2 |
| Emma | 800 | 3 |

---

# RANK()

Assigns ranking while allowing gaps.

Example

Sales

```
100

100

80
```

Ranks

```
1

1

3
```

---

# DENSE_RANK()

Assigns ranking without gaps.

Example

Sales

```
100

100

80
```

Ranks

```
1

1

2
```

---

# ROW_NUMBER vs RANK vs DENSE_RANK

| Function | Duplicate Values | Gaps |
|-----------|------------------|------|
| ROW_NUMBER | No | No |
| RANK | Yes | Yes |
| DENSE_RANK | Yes | No |

---

# NTILE()

Divides data into equal-sized groups.

Example

```sql
NTILE(4)
OVER(
ORDER BY Sales DESC
)
```

Business Example

Customer Segmentation

```
Top 25%

Second 25%

Third 25%

Bottom 25%
```

---

# LAG()

Returns the previous row value.

Example

```sql
LAG(Sales)
OVER(
ORDER BY Month
)
```

Useful for:

- Previous Month Sales
- Previous Day Stock Price
- Previous Transaction

---

# LEAD()

Returns the next row value.

Example

```sql
LEAD(Sales)
OVER(
ORDER BY Month
)
```

Useful for forecasting and trend analysis.

---

# FIRST_VALUE()

Returns the first value within the window.

Useful for:

- First Purchase
- Earliest Sale
- Initial Price

---

# LAST_VALUE()

Returns the last value within the window.

Useful for:

- Latest Purchase
- Most Recent Transaction
- Final Status

---

# Running Total

Example

```sql
SUM(Sales)
OVER(
ORDER BY Order_Date
)
```

Output

| Month | Sales | Running Total |
|--------|------:|--------------:|
| Jan |100|100|
| Feb |200|300|
| Mar |300|600|

---

# Moving Average

Example

```sql
AVG(Sales)
OVER(...)
```

Business Uses

- Trend Analysis
- Forecasting
- Financial Reports

---

# Window Aggregates

Aggregate functions can also be used as Window Functions.

Examples

```sql
SUM()

AVG()

COUNT()

MIN()

MAX()
```

Each preserves every row.

---

# GROUP BY vs Window Functions

| GROUP BY | Window Functions |
|----------|------------------|
| Reduces rows | Keeps all rows |
| One row per group | Every row retained |
| Summary reports | Analytical reports |

---

# Business Applications

Window Functions are widely used in:

- Sales Dashboards
- Revenue Trends
- Customer Rankings
- Running Totals
- Leaderboards
- Employee Performance
- Financial Reporting
- Inventory Analysis
- Time Series Analysis

---

# SQL Thinking Framework

Ask yourself:

```
Do I want

One Row Per Group?

↓

GROUP BY

----------------------

Keep Every Row?

↓

Window Function
```

---

# Interview Questions

- What are Window Functions?
- Difference between GROUP BY and Window Functions?
- Difference between ROW_NUMBER(), RANK(), and DENSE_RANK()?
- What is PARTITION BY?
- What is the OVER() clause?
- Explain LAG() and LEAD().
- What is a Running Total?
- What is a Moving Average?
- Business applications of Window Functions?

---

# Common Mistakes

❌ Confusing GROUP BY with Window Functions.

---

❌ Forgetting the OVER() clause.

---

❌ Using ROW_NUMBER() when duplicate rankings are required.

---

❌ Using RANK() when continuous ranking is expected.

---

# Key Takeaways

- Window Functions preserve every row.
- OVER() defines the calculation window.
- PARTITION BY creates logical groups.
- ORDER BY controls calculation sequence.
- ROW_NUMBER(), RANK(), and DENSE_RANK() solve ranking problems.
- LAG() and LEAD() compare adjacent rows.
- Running Totals and Moving Averages are common analytical techniques.

---

# 🚀 Session Progress

| Topic | Status |
|--------|--------|
| Introduction to Window Functions | ⏳ Pending |
| OVER() | ⏳ Pending |
| PARTITION BY | ⏳ Pending |
| ROW_NUMBER() | ⏳ Pending |
| RANK() | ⏳ Pending |
| DENSE_RANK() | ⏳ Pending |
| NTILE() | ⏳ Pending |
| LAG() | ⏳ Pending |
| LEAD() | ⏳ Pending |
| Running Totals | ⏳ Pending |
| Moving Average | ⏳ Pending |
| Business Problems | ⏳ Pending |
| Interview Questions | ⏳ Pending |

---

# 📈 Learning Outcome

This document will be updated as I learn and practice SQL Window Functions. By the end of this session, I aim to confidently solve ranking, trend analysis, running total, and analytical reporting problems commonly encountered in Data Analytics, Business Intelligence, and SQL interviews.

---

> **Next Session:** SQL Optimization, Query Performance, Indexing, Execution Plans, and Interview Case Studies.
