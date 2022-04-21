```
Source : https://leetcode.com/problems/user-activity-for-the-past-30-days-i/
Author : liuyubobobo
Time   : 2022-04-20
```

## Using GROUP BY

```MySQL
SELECT activity_date AS day, COUNT(DISTINCT user_id) AS active_users
FROM Activity
GROUP BY activity_date
HAVING DATEDIFF('2019-07-27', activity_date) < 30
```

```MySQL
SELECT activity_date AS day, COUNT(DISTINCT user_id) AS active_users
FROM Activity
WHERE DATEDIFF('2019-07-27', activity_date) < 30
GROUP BY activity_date
```
