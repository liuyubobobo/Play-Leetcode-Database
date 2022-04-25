```
Source : https://leetcode.com/problems/warehouse-manager/
Author : liuyubobobo
Time   : 2022-04-24
```

<br/>

## Using GROUP BY

```MySQL
SELECT Warehouse.name AS warehouse_name,
SUM(Products.Width * Products.Length * Products.Height * Warehouse.units) AS volume

FROM Warehouse JOIN Products
ON Warehouse.product_id = Products.product_id 
GROUP BY Warehouse.name
```

<br/>

## JOIN a temporary table

```MySQL
SELECT Warehouse.name AS warehouse_name, SUM(Warehouse.units * t.volume) AS volume

FROM Warehouse JOIN 
(
    SELECT product_id, Width * Length * Height AS volume
    FROM Products
) t

ON Warehouse.product_id = t.product_id 
GROUP BY Warehouse.name
```
