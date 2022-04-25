```
Source : https://leetcode.com/problems/queries-quality-and-percentage/
Author : liuyubobobo
Time   : 2022-04-25
```

## Using SUM / COUNT to get percentages

```MySQL
SELECT
    query_name,
    ROUND(AVG(rating / position), 2) AS quality,
    ROUND(SUM(rating < 3) / COUNT(*) * 100.0, 2) AS poor_query_percentage
FROM Queries
GROUP BY query_name
```

<br/>

## Using AVG only to get all the information

```MySQL
SELECT
    query_name,
    ROUND(AVG(rating / position), 2) AS quality,
    ROUND(AVG(rating < 3) * 100.0, 2) AS poor_query_percentage
FROM Queries
GROUP BY query_name
```
