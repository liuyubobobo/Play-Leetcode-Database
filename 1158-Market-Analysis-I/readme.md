```
Source : https://leetcode.com/problems/market-analysis-i/
Author : liuyubobobo
Time   : 2022-04-22
```

---

## Using LEFT JOIN

```MySQL
SELECT user_id AS buyer_id, join_date, COUNT(item_id) AS orders_in_2019
FROM Users LEFT JOIN Orders
ON user_id = buyer_id AND YEAR(order_date) = 2019 
GROUP BY user_id
```

Pay attention to the difference between WHERE and AND for filtering when using LEFT JOIN

<br/>

## Using Nested Subqueries

```MySQL
SELECT user_id AS buyer_id, join_date, 
(
    SELECT COUNT(item_id) 
    FROM Orders 
    WHERE Orders.buyer_id = Users.user_id AND YEAR(order_date) = 2019
) AS orders_in_2019
FROM Users
```
