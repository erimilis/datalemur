 
 # Second Highest Salary
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Second Highest Salary
* **Description:** Determine the second highest salary among all employees.
* **Approach:** `Row_number()` untuk menangani nilai gaji yang identik.
* **Links:** [Problem Link](https://datalemur.com/questions/sql-second-highest-salary)



### SQL Query
```

with xsalary as 
(SELECT salary
FROM employee
group by salary),

sortedsalary as (
select salary, row_number() over (order by salary desc) as ranking
from xsalary)

select salary as second_highest_salary
from sortedsalary
where ranking = 2


```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



