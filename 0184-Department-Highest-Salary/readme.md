```
Source : https://leetcode.com/problems/department-highest-salary/
Author : liuyubobobo
Time   : 2022-04-30
```

<br/>

## Nested Query

```MySQL
SELECT 
    Department.name AS Department, 
    E1.name AS Employee, 
    E1.salary AS Salary
FROM
    Employee AS E1, Department
WHERE E1.departmentId = Department.id
	  AND E1.salary =
	      (SELECT MAX(salary)
	      FROM Employee AS E2
	      WHERE E2.departmentId = E1.departmentId)
```
<br/>

## Another Version (From solution)

It's faster than above solution

```MySQL
SELECT 
    Department.name AS Department, 
    E1.name AS Employee, 
    E1.salary AS Salary
FROM
    Employee AS E1 JOIN Department ON E1.departmentId = Department.id
WHERE (E1.departmentId, E1.salary) IN
    (SELECT departmentId, MAX(salary)
	   FROM Employee
	   GROUP BY departmentId)
```