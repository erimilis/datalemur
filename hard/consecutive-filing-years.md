 # Consecutive Filing Years
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### 1. Consecutive Filing Years
* **Topic:** Gaps and Islands, Data Analytics
* **Description:** Identify users who have completed document submissions for 3 consecutive years.
* **Approach:** CTE, LEAD(), LAG(), atau ROW_NUMBER(), date subtraction.
* **Links:** [Problem Link](https://datalemur.com/questions/consecutive-filing-years)

### SQL Query
```
with a as (
SELECT user_id, EXTRACT(YEAR from filing_date) as yr,
CASE WHEN product like 'TurboTax%' THEN 'OK' END as turbo
FROM filed_taxes
ORDER BY user_id, filing_date
),
b as (
SELECT user_id,
CASE WHEN turbo = 'OK'
    THEN yr
END as y1,
CASE WHEN (user_id = LEAD(user_id) OVER w) and (LEAD(turbo) OVER W = 'OK')
    THEN LEAD(yr) OVER w
END as y2,
CASE WHEN (user_id = LEAD(user_id,2) OVER w) and (LEAD(turbo,2) OVER W = 'OK')
    THEN LEAD(yr,2) OVER w
END as y3
from a
window w as (ORDER BY user_id, yr)
)
SELECT user_id
from b
WHERE y2 = y1+1 and y3 = y1+2
group by user_id

```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)

[My Upwork Profile](https://upwork.com/freelancers/eriyawane)
[My Freelancer Profile](https://www.freelancer.com/u/erimilis)

