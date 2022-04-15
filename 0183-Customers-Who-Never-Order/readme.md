```
Source : https://leetcode.com/problems/customers-who-never-order/
Author : liuyubobobo
Time   : 2021-12-29
```

<br/>

## Nested Query

```MySQL
SELECT name AS Customers

FROM Customers

WHERE id NOT IN

(SELECT customerId FROM Orders)
```

<br/>

## Using LEFT JOIN

```MySQL
SELECT name AS Customers

FROM Customers LEFT JOIN Orders

ON Customers.id = Orders.customerId

WHERE Orders.id IS NULL
```