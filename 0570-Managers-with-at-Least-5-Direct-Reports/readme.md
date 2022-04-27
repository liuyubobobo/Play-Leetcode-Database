```
Source : https://leetcode.com/problems/managers-with-at-least-5-direct-reports/
Author : liuyubobobo
Time   : 2022-04-27
```

<br/>

## Using Nested Query

```MySQL
SELECT name FROM Employee WHERE id IN

(SELECT managerId
 FROM Employee
 GROUP BY managerId
 HAVING COUNT(*) >= 5)
```

<br/>

## Using JOIN

```MySQL
SELECT name 

FROM Employee JOIN

(SELECT managerId
 FROM Employee
 GROUP BY managerId
 HAVING COUNT(*) >= 5) AS Manager
 
 ON Employee.id = Manager.managerId
```