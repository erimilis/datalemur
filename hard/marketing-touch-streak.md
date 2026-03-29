 
 # Marketing Touch Streak
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Marketing Touch Streak
* **Description:** Generate a list of contact that satisfied three or more consecutive weeks and had at least one certain marketing touch.
* **Approach:** CTE, EXTRACT(week), WINDOW.
* **Links:** [Problem Link](https://datalemur.com/questions/marketing-touch-streak)

### SQL Query
```

WITH weekly_data as (
SELECT contact_id, event_type, extract(week from event_date) as wk 
FROM marketing_touches
group by contact_id, wk, event_type
order by contact_id, wk, event_type),

rekap as (
select contact_id,
wk,
lead(wk) over w as wk2, 
lead(wk, 2) over w as wk3,
event_type as ev1,
lead(event_type) over w as ev2,
lead(event_type, 2) over w as ev3
from weekly_data
window w as (partition by contact_id order by wk)),

marketing as (
select * from rekap
where wk2 is not NULL and wk3 is not NULL
and wk2 = wk +1 and wk3 = wk2 +1
and (ev1 = 'trial_request' or ev2 = 'trial_request' or ev3 = 'trial_request'))

select email
from marketing
join crm_contacts on marketing.contact_id = crm_contacts.contact_id
order by email

```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



