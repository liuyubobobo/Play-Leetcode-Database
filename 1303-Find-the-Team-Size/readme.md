```
Source : https://leetcode.com/problems/find-the-team-size/
Author : liuyubobobo
Time   : 2022-04-27
```

---

## Using JOIN

```MySQL
SELECT Employee.employee_id, t.team_size
FROM Employee JOIN
(SELECT team_id, COUNT(*) AS team_size FROM Employee GROUP BY team_id) t
ON Employee.team_id = t.team_id
```

<br/>

## Using Nested Query

```MySQL
SELECT e1.employee_id, 
(SELECT COUNT(*) 
 FROM Employee AS e2 
 WHERE e1.team_id = e2.team_id 
 GROUP BY team_id) AS team_size
 
FROM Employee AS e1
```