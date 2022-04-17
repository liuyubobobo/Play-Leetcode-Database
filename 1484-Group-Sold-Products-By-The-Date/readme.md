```
Source : https://leetcode.com/problems/group-sold-products-by-the-date/
Author : liuyubobobo
Time   : 2022-04-16
```

<br/>

## Using GROUP_CONCAT

```MySQL
SELECT 
sell_date, 
COUNT(DISTINCT product) AS num_sold, 
GROUP_CONCAT(DISTINCT product ORDER BY product SEPARATOR ',') AS products
FROM Activities
GROUP BY sell_date
ORDER BY sell_date
```
