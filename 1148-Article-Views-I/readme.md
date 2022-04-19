```
Source : https://leetcode.com/problems/article-views-i/
Author : liuyubobobo
Time   : 2022-04-18
```

---

```MySQL
SELECT DISTINCT author_id AS id
FROM Views
WHERE author_id = viewer_id
ORDER BY author_id
```

