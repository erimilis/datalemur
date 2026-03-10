 
 # Repeated Payments
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Repeated Payments
* **Topic:** Self-Join, Time-Series Analysis
* **Description:** Detects repeat transactions (same amount & merchant) within a time span of < 10 minutes.
* **Approach:** CTE, EXTRACT(EPOCH FROM ...) filtering.
* **Links:** [Problem Link](https://datalemur.com/questions/repeated-payments)

### SQL Query
```

with a as (
SELECT id, merchant_id, credit_card_id, amount, transaction_timestamp,
 lead(merchant_id) over w as merchant_id2,
 lead(credit_card_id) over w as credit_card_id2,
 lead(amount) over w as amount2,
 lead(transaction_timestamp) over w as timestamp2
FROM transactions
window w as (order by merchant_id, credit_card_id, amount, transaction_timestamp)
),

b as (
select *, (EXTRACT(EPOCH FROM (timestamp2 - transaction_timestamp)) / 60) as selisih
from a
where merchant_id = merchant_id2 and credit_card_id = credit_card_id2
and amount = amount2
)

select count(*) as payment_count from b where selisih <= 10

```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



