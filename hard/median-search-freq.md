 
 # Median Google Search Frequency
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Median Google Search Frequency
* **Description:** Find median from a search frequency table.
* **Approach:** CTE, WINDOW.
* **Links:** [Problem Link](https://datalemur.com/questions/median-search-freq)

### SQL Query
```

with gmed as (
SELECT div(sum(num_users),2) as med1, 
mod(sum(num_users),2) as med2 
FROM search_frequency),

gmedx as (
select med1, case when med2=0 then 1 end as med2
from gmed
),

bahan as (
select searches, sum(num_users) over w as total
from search_frequency
window w as (order by searches)),

median1 as (
select searches from bahan
left join gmed on 1=1
where total >= gmed.med1
limit 1),

median2 as (
select searches from bahan
left join gmedx on 1=1
where total >= gmedx.med1+gmedx.med2
limit 1)

select
-- median1.searches, median2.searches,
-- (median1.searches+median2.searches) as medtot,
(median1.searches+median2.searches)::float /2 as median
from median1 join median2 on 1=1

```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



