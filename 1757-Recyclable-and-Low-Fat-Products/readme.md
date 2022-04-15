```
Source : https://leetcode.com/problems/recyclable-and-low-fat-products/
Author : liuyubobobo
Time   : 2022-04-14
```

<br/>

## Using AND

```MySQL
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y'
```