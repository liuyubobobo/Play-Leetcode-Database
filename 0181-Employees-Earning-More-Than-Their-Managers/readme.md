```
Source : https://leetcode.com/problems/employees-earning-more-than-their-managers/
Author : liuyubobobo
Time   : 2021-12-29
```

<br/>

## Using Nested Query

```MySQL
SELECT name as Employee

FROM Employee

WHERE salary > 

(SELECT salary from Employee AS Manager WHERE Employee.managerId = Manager.id);
```
<br/>

## Using JOIN

```MySQL
SELECT a.name AS Employee

FROM Employee AS a, Employee AS b

WHERE a.salary > b.salary AND a.managerId = b.Id; 
```