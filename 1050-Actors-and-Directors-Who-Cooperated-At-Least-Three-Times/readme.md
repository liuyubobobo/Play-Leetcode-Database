```
Source : https://leetcode.com/problems/actors-and-directors-who-cooperated-at-least-three-times/
Author : liuyubobobo
Time   : 2022-04-22
```

<br/>

## Using GROUP BY

```MySQL
SELECT actor_id, director_id
FROM ActorDirector
GROUP BY actor_id, director_id
HAVING COUNT(timestamp) >= 3
```

<br/>