```
Source : https://leetcode.com/problems/find-followers-count/
Author : liuyubobobo
Time   : 2022-04-20
```

<br/>

## Using GROUP BY

```MySQL
SELECT user_id, COUNT(*) AS followers_count
FROM Followers
GROUP BY user_id
ORDER BY user_id 
```

