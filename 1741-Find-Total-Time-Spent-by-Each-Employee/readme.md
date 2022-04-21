```
Source : https://leetcode.com/problems/find-total-time-spent-by-each-employee/
Author : liuyubobobo
Time   : 2022-04-21
```

<br/>

## Using SUM

```MySQL
SELECT event_day AS day, emp_id, SUM(out_time - in_time) AS total_time
FROM Employees
GROUP BY event_day, emp_id
```

