```
Source : https://leetcode.com/problems/customer-placing-the-largest-number-of-orders/
Author : liuyubobobo
Time   : 2022-04-21
```

<br/>

## Using ORDER BY and LIMIT 1 to get the only one MAX

```MySQL
SELECT customer_number
FROM Orders
GROUP BY customer_number
ORDER BY COUNT(*) DESC 
LIMIT 1
```

<br/>

## To handle multiple MAX

Using ORDER BY and LIMIT 1 first to get max value and using sub queries.

```MySQL
SELECT customer_number
FROM Orders
GROUP BY customer_number
HAVING COUNT(*) = 
(SELECT COUNT(*) FROM Orders GROUP BY customer_number ORDER BY COUNT(*) DESC LIMIT 1)

```
