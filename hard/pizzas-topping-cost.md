 
 # Three Toping Pizzas
### DataLemur Hard Challenge

Below are my completed solutions to SQL challenges on [DataLemur](https://datalemur.com/).

This page serves as a portfolio of my skills in solving business problems using advanced query techniques.

### Three Toping Pizzas
* **Description:** Generate a list of cost of 3 topping pizza combinations.
* **Approach:** CTE, WINDOW.
* **Links:** [Problem Link](https://datalemur.com/questions/pizzas-topping-cost)


### SQL Query
```

select a.topping_name ||','|| b.topping_name ||','|| c.topping_name as pizza,
a.ingredient_cost + b.ingredient_cost + c.ingredient_cost as total_cost
FROM pizza_toppings as a
JOIN pizza_toppings as b on b.topping_name > a.topping_name
JOIN pizza_toppings as c on c.topping_name > b.topping_name
ORDER BY total_cost desc, a.topping_name, b.topping_name, c.topping_name

```

[My LinkedIn Link](https://id.linkedin.com/in/eriyawan)
[My Profile on HackerRank](https://www.hackerrank.com/profile/erimilis)
[My Profile on Leetcode](https://leetcode.com/u/erimilis)



