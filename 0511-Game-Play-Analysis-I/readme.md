```
Source : https://leetcode.com/problems/game-play-analysis-i/
Author : liuyubobobo
Time   : 2022-04-21
```

<br/>

## Using MIN

```MySQL
SELECT player_id, MIN(event_date) AS first_login
FROM Activity
GROUP BY player_id
```
