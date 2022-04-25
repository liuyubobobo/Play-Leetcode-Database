```
Source : https://leetcode.com/problems/percentage-of-users-attended-a-contest/
Author : liuyubobobo
Time   : 2022-04-25
```

<br/>

---

```MySQL
SELECT 
  contest_id, 
  ROUND(COUNT(user_id) / (SELECT COUNT(*) FROM Users) * 100.0, 2) AS percentage
FROM Register
GROUP BY contest_id
ORDER BY COUNT(user_id) DESC, contest_id ASC
```
