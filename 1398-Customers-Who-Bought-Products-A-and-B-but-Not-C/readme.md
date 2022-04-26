```
Source : https://leetcode.com/problems/customers-who-bought-products-a-and-b-but-not-c/
Author : liuyubobobo
Time   : 2022-04-26
```

<br/>

## Big WHERE

```MySQL
SELECT customer_id, customer_name 
FROM Customers
WHERE 
customer_id IN (SELECT customer_id FROM Orders WHERE product_name = 'A') AND
customer_id IN (SELECT customer_id FROM Orders WHERE product_name = 'B') AND
customer_id NOT IN (SELECT customer_id FROM Orders WHERE product_name = 'C')
```

<br/>

## Using JOIN and GROUP BY

```MySQL
SELECT Customers.customer_id, Customers.customer_name 
FROM Customers JOIN Orders
ON Customers.customer_id = Orders.customer_id
GROUP BY Customers.customer_id
HAVING SUM(product_name = 'A') > 0 AND SUM(product_name = 'B') > 0 AND SUM(product_name = 'C') = 0
```

