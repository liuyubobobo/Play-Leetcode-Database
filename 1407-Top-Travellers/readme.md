```
Source : https://leetcode.com/problems/top-travellers/
Author : liuyubobobo
Time   : 2022-04-22
```

<br/>

## Using LEFT JOIN

```MySQL
SELECT name, IFNULL(SUM(distance), 0) AS travelled_distance
FROM Users LEFT JOIN Rides
ON Users.id = Rides.user_id
GROUP BY Users.id
ORDER BY travelled_distance DESC, name ASC
```

<br/>

## Using Subqueries

```MySQL
SELECT name, 
(SELECT IFNULL(SUM(distance), 0)
 FROM Rides
 WHERE Users.id = Rides.user_id 
)AS travelled_distance
FROM Users
ORDER BY travelled_distance DESC, name ASC
```
