 
 # Histogram of Tweets
### DataLemur Easy Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Histogram of Tweets
* **Topic:** Basic Aggregation
* **Description:** Create a distribution of the number of tweets sent by users in 2022.
* **Approach:** Double `GROUP BY` (Nested Aggregation).
* **Links:** [Problem Link](https://datalemur.com/questions/sql-histogram-tweets)


### SQL Query
```

with a as 
(select user_id, count(*) as cc 
FROM tweets where EXTRACT(year from tweet_date) = 2022 
group by user_id)

select cc as tweet_bucket, count(*) as user_num 
from a group by cc order by cc;


```


[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)

[My Upwork Profile](https://upwork.com/freelancers/eriyawane)
[My Freelancer Profile](https://www.freelancer.com/u/erimilis)





