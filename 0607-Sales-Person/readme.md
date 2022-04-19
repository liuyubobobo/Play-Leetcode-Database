```
Source : https://leetcode.com/problems/sales-person/
Author : liuyubobobo
Time   : 2022-04-18
```

<br/>

## Using Nested Query

```MySQL
SELECT name
FROM SalesPerson
WHERE sales_id NOT IN
(SELECT sales_id FROM Orders WHERE com_id IN
 (SELECT com_id FROM Company WHERE name = "RED"))
```

<br/>

## Using LEFT JOIN

```MySQL
SELECT name
FROM SalesPerson
WHERE sales_id NOT IN
(SELECT sales_id 
 FROM Orders LEFT JOIN Company
 ON Orders.com_id = Company.com_id
 WHERE Company.name = "RED")
```