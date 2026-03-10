# 🚀 My SQL Portfolio
### DataLemur Challenge Solutions

This repository contains a collection of solutions I've completed to SQL challenges on [DataLemur](https://datalemur.com/).

The purpose of this repository is to serve as a portfolio of my skills in solving business problems using advanced query techniques.

---



[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)
---

## 🔴 Hard Challenges

### 1. Consecutive Filing Years
* **Topic:** Gaps and Islands, Data Analytics
* **Description:** Identify users who have completed document submissions for 3 consecutive years.
* **Approach:** CTE, LEAD(), LAG(), atau ROW_NUMBER(), date subtraction.
* **Links:** [Solustion Link](hard/consecutive-filing-years.md) | [Problem Link](https://datalemur.com/questions/consecutive-filing-years)

### 2. Repeated Payments
* **Topic:** Self-Join, Time-Series Analysis
* **Description:** Detects repeat transactions (same amount & merchant) within a time span of < 10 minutes.
* **Approach:** CTE, EXTRACT(EPOCH FROM ...) filtering.
* **Links:** [Solustion Link](https://datalemur.com/questions/consecutive-filing-years) | [Problem Link](https://datalemur.com/questions/repeated-payments)

### 3. Reactivated Users
* **Topic:** User Retention, Month-over-Month Analysis
* **Description:** Counts the number of users who returned to activity after a period of inactivity.
* **Approach:** CTE, LAG(), mapping.
* **Links:** [Solustion Link](https://datalemur.com/questions/consecutive-filing-years) | [Problem Link](https://datalemur.com/questions/reactivated-users)

---

## 🟡 Medium Challenges

### 1. Highest Grossing Items
* **Topic:** Ranking, Aggregations
* **Description:** Find the 2 highest-grossing products per category in a given year..
* **Approach:** `RANK()` atau `DENSE_RANK()` di dalam CTE.
* **Links:** [Solustion Link](https://datalemur.com/questions/consecutive-filing-years) | [Problem Link](https://datalemur.com/questions/sql-highest-grossing)

### 2. Top Three Salaries
* **Topic:** Window Functions
* **Description:** Displays the top 3 unique salaries per department.
* **Approach:** `DENSE_RANK()` untuk menangani nilai gaji yang identik.
* **Links:** [Solustion Link](https://datalemur.com/questions/consecutive-filing-years) | [Problem Link](https://datalemur.com/questions/sql-top-three-salaries)

---

## 🟢 Easy Challenges

### 1. Histogram of Tweets
* **Topic:** Basic Aggregation
* **Description:** Create a distribution of the number of tweets sent by users in 2022.
* **Approach:** Double `GROUP BY` (Nested Aggregation).
* **Links:** [Solustion Link](https://datalemur.com/questions/consecutive-filing-years) | [Problem Link](https://datalemur.com/questions/sql-histogram-tweets)

### 2. Contains Duplicates (Python)
* **Topic:** Array & Hash Set Logic
* **Description:** Checks whether there are duplicate values ​​in the list.
* **Approach:** Comparing list length and set length.
* **Links:** [Solustion Link](https://datalemur.com/questions/consecutive-filing-years) | [Problem Link](https://datalemur.com/questions/python-contains-duplicate)

---

## 🛠️ Tech Stack
* **SQL:** PostgreSQL (Standard Environment)
* **Python:** Basic Data Structures
* **Skills:** Window Functions, CTEs, Time-Series Analysis, Query Optimization.



