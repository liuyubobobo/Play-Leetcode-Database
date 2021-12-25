## Using Nested Query

SELECT name as Employee

FROM Employee

WHERE salary > 

(SELECT salary from Employee AS Manager WHERE Employee.managerId = Manager.id);

<br/>

## Using JOIN

\# JOIN is faster than nested query

SELECT a.name AS Employee

FROM Employee AS a, Employee AS b

WHERE a.salary > b.salary AND a.managerId = b.Id; 
