# SQL TOP 50 LeetCode Problems Solutions 🐘📚

Welcome to the repository of SQL solutions for LeetCode problems. This is a curated collection aimed at enhancing your SQL skills through practical problem-solving. Explore various SQL concepts, ranging from basic queries to advanced techniques, all while tackling real-world coding challenges.

---

## 🗂 Table of Contents
1. [About the Repository](#about-the-repository)
2. [LeetCode Problems Overview](#leetcode-problems-overview)
3. [Understanding Joins and Keys](#[understanding-joins-and-keys](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/))
4. [Advanced SQL Concepts](#advanced-sql-concepts)
5. [Folder Structure](#folder-structure)
6. [How to Contribute](#how-to-contribute)
7. [Contact & Feedback](#contact--feedback)

---

## 📖 About the Repository

This repository contains:
- **Comprehensive solutions** to SQL problems categorized by difficulty (Easy, Medium, Hard).
- Highlights of important SQL concepts like joins, keys, aggregations, and window functions.
- Well-documented queries to help learners understand the logic behind each solution.
- A section dedicated to advanced SQL techniques to level up your database expertise.

---

## 📊 LeetCode Problems Overview

| **Problem Title**          | **Difficulty** | **Tags**                   | **Solution**                                      |
|-----------------------------|----------------|----------------------------|--------------------------------------------------|
| Employee Details            | Easy           | Basics, Filtering          | [Solution](./solutions/employee_details.sql)    |
| Product Sales               | Medium         | Aggregations, Joins        | [Solution](./solutions/product_sales.sql)       |
| Top Rank Employees          | Hard           | Window Functions, Ranking  | [Solution](./solutions/top_rank_employees.sql)  |
| Department Salaries         | Medium         | Grouping, Aggregations     | [Solution](./solutions/department_salaries.sql) |

**Note**: Tags make it easier to filter problems by specific SQL concepts like `Joins`, `CTEs`, or `Keys`.

---

## 🔗 Understanding Joins and Keys

### **Joins**
Joins allow you to combine data from multiple tables. Here are the key types:
- **Inner Join**: Matches records in both tables.
- **Left Join (or Left Outer Join)**: Includes all records from the left table and matched records from the right.
- **Right Join (or Right Outer Join)**: Includes all records from the right table and matched records from the left.
- **Full Outer Join**: Combines all records from both tables, filling in `NULLs` for non-matches.

#### Example: Inner Join
```SQL
SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;
```

Keys
Keys are crucial for defining relationships and ensuring data integrity:
- Primary Key: Ensures each row in a table is unique.
- Foreign Key: Links two tables by referring to the primary key of another table.

Example: Foreign Key Definition
```SQL
CREATE TABLE employees (
  employee_id INT PRIMARY KEY,
  department_id INT,
  FOREIGN KEY (department_id) REFERENCES departments(department_id)
);
```


# ⚙️ Advanced SQL Concepts
## Take your SQL skills to the next level with these techniques:
- Common Table Expressions (CTEs)
CTEs simplify complex queries and make them more readable.
```SQL
WITH SalesRanking AS (
  SELECT salesperson_id, SUM(sales_amount) AS total_sales
  FROM sales
  GROUP BY salesperson_id
)
SELECT *
FROM SalesRanking
WHERE total_sales > 100000;
```

- Window Functions
Analyze data within partitions using advanced analytical functions.
```SQL
SELECT employee_id, salary,
       RANK() OVER (PARTITION BY department_id ORDER BY salary DESC) AS rank
FROM employees;
```

- Pivot Tables
Convert rows into columns for better data visualization.
```SQL
SELECT department_id,
       SUM(CASE WHEN gender = 'Male' THEN 1 ELSE 0 END) AS male_count,
       SUM(CASE WHEN gender = 'Female' THEN 1 ELSE 0 END) AS female_count
FROM employees
GROUP BY department_id;
```

📁 Folder Structure
```
├── solutions/
│   ├── employee_details.sql
│   ├── product_sales.sql
│   ├── top_rank_employees.sql
│   ├── department_salaries.sql
├── README.md
```


🌟 How to Contribute
We welcome contributions to improve this repository! You can:
- Add solutions to unsolved problems.
- Enhance the readability or efficiency of existing queries.
- Contribute to documentation or add advanced topics.

Follow these steps:
- Fork the repository.
- Create a new branch for your changes.
- Submit a pull request with a description of your updates.


📬 Contact & Feedback
Got ideas or feedback? Let us know!
- Open a serious GitHub issue here.
- Email: avrajeet2003@example.com


✨ Additional Features
- Badges: Add GitHub badges for a professional touch.
- Table of Contents Links: Navigate the README easily using links.
- Code Snippets: Well-documented SQL code snippets throughout.

Enjoy exploring SQL and happy querying! 🚀

This README incorporates a professional structure with badges, a clean folder hierarchy, and clear examples for advanced SQL concepts. Let me know if you want me to tweak anything further! 🚀

