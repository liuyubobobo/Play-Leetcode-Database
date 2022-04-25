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
