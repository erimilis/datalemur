 
 # Highest Grossing Items
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Highest Grossing Items
* **Topic:** Ranking, Aggregations
* **Description:** Find the 2 highest-grossing products per category in a given year..
* **Approach:** `RANK()` atau `DENSE_RANK()` di dalam CTE.
* **Links:** [Problem Link](https://datalemur.com/questions/sql-highest-grossing)


### SQL Query
```

with a as
(SELECT category, product, sum(spend) as total_spend
FROM product_spend where EXTRACT(YEAR from transaction_date) = 2022
group by category, product
order by category, total_spend desc),

b as
(SELECT category, product, total_spend, row_number() over(
  partition by category
  order by total_spend desc
) as rn
FROM a)

select category, product, total_spend from b
where rn <= 2


```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



