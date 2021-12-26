## Nested Query

SELECT name AS Customers

FROM Customers


WHERE id NOT IN

(SELECT customerId FROM Orders)

<br/>

## Using LEFT JOIN

SELECT name AS Customers

FROM Customers LEFT JOIN Orders

ON Customers.id = Orders.customerId

WHERE Orders.id IS NULL
