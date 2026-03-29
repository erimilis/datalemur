 
 # Y-on-Y Growth Rate
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### 8. Y-on-Y Growth Rate
* **Description:** Calculate the year-on-year growth rate for the total spend of each product, grouping the results by product.
* **Approach:** CTE, WINDOW.
* **Links:** [Problem Link](https://datalemur.com/questions/yoy-growth-rate)


### SQL Query
```

with yearspend as (
SELECT extract(year from TRANSACTION_date) as year, 
product_id, sum(spend) as spend 
FROM user_transactions
group by year, product_id),

rekap as (
select year, product_id, spend as curr_year_spend,
lag(year) over w as prevyear,
lag(product_id) over w as prevproduct,
lag(spend) over w as prev_year_spend
from yearspend
window w as (partition by product_id order by product_id, year)
)

select year, product_id, curr_year_spend, prev_year_spend, 
round(((curr_year_spend-prev_year_spend)/prev_year_spend)*100,2) as yoy
from rekap

```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



