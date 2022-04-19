```
Source : https://leetcode.com/problems/rising-temperature/
Author : liuyubobobo
Time   : 2022-04-19
```

<br/>

## Using Nested Query AND DATE_SUB

```MySQL
SELECT id 
FROM Weather AS W1
WHERE temperature  > 
(SELECT temperature FROM Weather AS W2 
 WHERE W2.recordDate = DATE_SUB(W1.recordDate, INTERVAL 1 DAY))
```

<br/>

## Using Nested Query AND DATEDIFF

```MySQL
SELECT id 
FROM Weather AS W1
WHERE temperature  > 
(SELECT temperature FROM Weather AS W2 
 WHERE DATEDIFF(W1.recordDate, W2.recordDate) = 1)
```

<br/>

## JOIN

```MySQL
SELECT W1.id AS "id"
FROM Weather AS W1 JOIN Weather AS W2
ON DATEDIFF(W1.recordDate, W2.recordDate) = 1 
WHERE W1.temperature > W2.temperature
```