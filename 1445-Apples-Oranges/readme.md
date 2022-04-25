```
Source : https://leetcode.com/problems/apples-oranges/
Author : liuyubobobo
Time   : 2022-04-24
```

<br/>

## Using CASE

```MySQL
SELECT sale_date, 
    SUM(
        CASE WHEN fruit = 'apples' THEN sold_num
        ELSE -sold_num END
    ) AS diff
FROM Sales
GROUP BY sale_date
```

<br/>

## Using IF

```MySQL
SELECT sale_date, 
    SUM(
        IF(fruit = 'apples', sold_num, -sold_num)
    ) AS diff
FROM Sales
GROUP BY sale_date
```

<br/>

## Using JOIN

```MySQL
SELECT apples.sale_date, apples.sold_num - oranges.sold_num AS diff
FROM
	(SELECT sale_date, sold_num FROM Sales WHERE fruit = 'apples') AS apples
	JOIN
	(SELECT sale_date, sold_num FROM sales WHERE fruit = 'oranges') AS oranges

ON apples.sale_date = oranges.sale_date
GROUP BY apples.sale_date
```

