 
 # Top Three Salaries
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Top Three Salaries
* **Topic:** Window Functions
* **Description:** Displays the top 3 unique salaries per department.
* **Approach:** `DENSE_RANK()` untuk menangani nilai gaji yang identik.
* **Links:** [Problem Link](https://datalemur.com/questions/sql-top-three-salaries)


### SQL Query
```

with a AS
(
SELECT department_id, salary,
row_number() OVER (
   partition by department_id
   order by salary desc
) as rslt
FROM employee
group by department_id, salary
)

select department_name, name, a.salary
from a 
join department on department.department_id=a.department_id
join employee on employee.salary = a.salary and employee.department_id=a.department_id
where a.rslt <= 3
order by department.department_name, a.salary desc, name


```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



