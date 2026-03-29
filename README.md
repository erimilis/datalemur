# 🚀 My SQL Portfolio
### DataLemur Challenge Solutions

This repository contains my personal solutions to various DataLemur challenges, implemented in **PostgreSQL**, and **Python**. It serves as a record of my problem-solving journey and a reference for different algorithmic approaches.

---
![profile](img/profile_ss.png)

My profile link: [LinkedIn](https://id.linkedin.com/in/eriyawan) | [HackerRank](https://www.hackerrank.com/profile/erimilis) | [Leetcode](https://leetcode.com/u/erimilis)
---

## 🔴 Hard Challenges

### 1. Consecutive Filing Years
* **Description:** Identify users who have completed document submissions for 3 consecutive years.
* **Approach:** CTE, LEAD(), LAG(), atau ROW_NUMBER(), date subtraction.
* **Links:** [Solustion Link](hard/consecutive-filing-years.md) | [Problem Link](https://datalemur.com/questions/consecutive-filing-years)

### 2. Repeated Payments
* **Description:** Detects repeat transactions (same amount & merchant) within a time span of < 10 minutes.
* **Approach:** CTE, EXTRACT(EPOCH FROM ...) filtering.
* **Links:** [Solustion Link](hard/repeated-payments.md) | [Problem Link](https://datalemur.com/questions/repeated-payments)

### 3. Reactivated Users
* **Description:** Counts the number of users who returned to activity after a period of inactivity.
* **Approach:** CTE, LAG(), mapping.
* **Links:** [Solustion Link](hard/reactivated-users.md) | [Problem Link](https://datalemur.com/questions/reactivated-users)

### 4. Median Google Search Frequency
* **Description:** Find median from a search frequency table.
* **Approach:** CTE, WINDOW.
* **Links:** [Solustion Link](hard/median-search-freq.md) | [Problem Link](https://datalemur.com/questions/median-search-freq)

### 5. Server Utilization Time
* **Description:** Find server utilization from a status session table.
* **Approach:** CTE, WINDOW. EXTRACT(DAY, HOUR)
* **Links:** [Solustion Link](hard/total-utilization-time.md) | [Problem Link](https://datalemur.com/questions/total-utilization-time)

### 6. Marketing Touch Streak
* **Description:** Generate a list of contact that satisfied three or more consecutive weeks and had at least one certain marketing touch.
* **Approach:** CTE, EXTRACT(week), WINDOW.
* **Links:** [Solustion Link](hard/marketing-touch-streak.md) | [Problem Link](https://datalemur.com/questions/marketing-touch-streak)

### 7. Three Toping Pizzas
* **Description:** Generate a list of cost of 3 topping pizza combinations.
* **Approach:** CTE, WINDOW.
* **Links:** [Solustion Link](hard/pizzas-topping-cost.md) | [Problem Link](https://datalemur.com/questions/pizzas-topping-cost)

### 8. Y-on-Y Growth Rate
* **Description:** Calculate the year-on-year growth rate for the total spend of each product, grouping the results by product.
* **Approach:** CTE, WINDOW.
* **Links:** [Solustion Link](hard/yoy-growth-rate.md) | [Problem Link](https://datalemur.com/questions/yoy-growth-rate)


---

## 🟡 Medium Challenges

### 1. Highest Grossing Items
* **Description:** Find the 2 highest-grossing products per category in a given year..
* **Approach:** `Row_number()` di dalam CTE.
* **Links:** [Solustion Link](medium/sql-highest-grossing.md) | [Problem Link](https://datalemur.com/questions/sql-highest-grossing)

### 2. Top Three Salaries
* **Description:** Displays the top 3 unique salaries per department.
* **Approach:** `DENSE_RANK()` untuk menangani nilai gaji yang identik.
* **Links:** [Solustion Link](medium/sql-top-three-salaries.md) | [Problem Link](https://datalemur.com/questions/sql-top-three-salaries)

### 3. Second Highest Salary
* **Description:** Determine the second highest salary among all employees.
* **Approach:** `Row_number()` untuk menangani nilai gaji yang identik.
* **Links:** [Solustion Link](medium/sql-second-highest-salary.md) | [Problem Link](https://datalemur.com/questions/sql-second-highest-salary)


---

## 🟢 Easy Challenges

### 1. Histogram of Tweets
* **Description:** Create a distribution of the number of tweets sent by users in 2022.
* **Approach:** Double `GROUP BY` (Nested Aggregation).
* **Links:** [Solustion Link](easy/sql-histogram-tweets.md) | [Problem Link](https://datalemur.com/questions/sql-histogram-tweets)

### 2. Contains Duplicates (Python)
* **Description:** Checks whether there are duplicate values ​​in the list.
* **Approach:** Comparing list length and set length.
* **Links:** [Solustion Link](easy/python-contains-duplicate.md) | [Problem Link](https://datalemur.com/questions/python-contains-duplicate)

### 3. Is Palindrome (Python)
* **Description:** Checks whether a string is palindrom.
* **Approach:** Comparing list length and set length.
* **Links:** [Solustion Link](easy/python-palindrome.md) | [Problem Link](https://datalemur.com/questions/python-palindrome)

---

## 🛠️ Tech Stack
* **SQL:** PostgreSQL (Standard Environment)
* **Python:** Basic Data Structures
* **Skills:** Window Functions, CTEs, Time-Series Analysis, Query Optimization.



