```
Source : https://leetcode.com/problems/page-recommendations/
Author : liuyubobobo
Time   : 2022-04-27
```

---

## Nested Query

```MySQL
SELECT DISTINCT page_id AS recommended_page
FROM Likes
WHERE page_id IN
(SELECT page_id FROM Likes WHERE user_id IN
  ((SELECT user1_id as friend_id FROM Friendship WHERE user2_id = 1)
    UNION
   (SELECT user2_id as friend_id FROM Friendship WHERE user1_id = 1))
)
AND page_id NOT IN
( SELECT page_id FROM Likes WHERE user_id = 1)
```

<br/>

## Using JOIN

```MySQL
SELECT DISTINCT page_id AS recommended_page

FROM 
(SELECT (CASE WHEN user1_id = 1 THEN user2_id 
              WHEN user2_id = 1 THEN user1_id END) AS user_id FROM Friendship
) t JOIN Likes ON t.user_id = Likes.user_id

WHERE page_id NOT IN
(SELECT page_id FROM Likes WHERE user_id = 1)
```