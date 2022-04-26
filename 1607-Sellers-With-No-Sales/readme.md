```
Source : https://leetcode.com/problems/sellers-with-no-sales/
Author : liuyubobobo
Time   : 2022-04-26
```

<br/>

## Using Nested Query

```MySQL
SELECT seller_name 
FROM Seller 
WHERE seller_id NOT IN
(
    SELECT seller_id FROM Orders
    WHERE YEAR(sale_date) = 2020
)
ORDER BY seller_name ASC
```
