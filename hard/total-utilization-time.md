 
 # Server Utilization Time
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Server Utilization Time
* **Topic:** Frequency, Statistic
* **Description:** Find server utilization from a status session table.
* **Approach:** CTE, WINDOW. EXTRACT(DAY, HOUR)
* **Links:** [Problem Link](https://datalemur.com/questions/total-utilization-time)


### SQL Query
```

with a as (
SELECT *, 
  LEAD(server_id) over w as server2,
  LEAD(session_status) over w as status2,
  LEAD(status_time) over w as time2
FROM server_utilization 
window w as (order by server_id, status_time)),

b as (
select * from a
where server_id = server2 and session_status = 'start'),

c as (
select server_id, time2, status_time,
EXTRACT(DAY from (time2 - status_time)) as drsd,
EXTRACT(HOUR from (time2 - status_time)) as drsh
from b),

d as (
select sum(drsd) as xday, sum(drsh) as xhour from c)

select xday + div(xhour, 24) as total_uptime_days from d

```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



