 
 # Reactivated Users
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Reactivated Users
* **Topic:** User Retention, Month-over-Month Analysis
* **Description:** Counts the number of users who returned to activity after a period of inactivity.
* **Approach:** CTE, LAG(), mapping.
* **Links:** [Problem Link](https://datalemur.com/questions/reactivated-users)


### SQL Query
```

with a AS (
SELECT user_id, login_date,
    lag(user_id) over w as last_user,
    lag(login_date) over w as last_login
FROM user_logins
window w as (order by user_id, login_date)
),

b as (
SELECT user_id, login_date, 
CASE 
  WHEN user_id=last_user THEN last_user ELSE null 
END as last_user,
CASE
  WHEN user_id=last_user THEN last_login ELSE null
END as last_login
from a
),

c as (
select user_id, last_user, 
EXTRACT(MONTH from login_date) as m1, 
COALESCE(EXTRACT(MONTH from last_login),-1) as m2, 
login_date, last_login
from b
)

select m1 as mth, count(*) as reactivated_users
from c
where m1-m2 > 1
group by m1
order by m1



```


[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)


