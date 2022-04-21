```
Source : https://leetcode.com/problems/the-latest-login-in-2020/
Author : liuyubobobo
Time   : 2022-04-21
```

<br/>

## Using GROUP BY

```MySQL
SELECT user_id, MAX(time_stamp) AS last_stamp
FROM Logins
WHERE time_stamp >= '2020-01-01' AND time_stamp < '2021-01-01'
GROUP BY user_id
```

<br/>

## Using YEAR

```MySQL
SELECT user_id, MAX(time_stamp) AS last_stamp
FROM Logins
WHERE YEAR(time_stamp) = 2020
GROUP BY user_id
```
