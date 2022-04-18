```
Source : https://leetcode.com/problems/tree-node/
Author : liuyubobobo
Time   : 2022-04-18
```

<br/>

## Using UNION

```MySQL
SELECT id, "Root" AS Type 
FROM tree
WHERE p_id IS NULL

UNION

SELECT id, "Inner" AS Type 
FROM tree
WHERE id IN (SELECT p_id FROM tree) AND id NOT IN (SELECT id FROM tree WHERE p_id IS NULL)

UNION

SELECT id, "Leaf" AS Type
FROM tree
WHERE id NOT IN (SELECT p_id FROM tree)

ORDER BY id

```

<br/>

## Using CASE

```MySQL
SELECT id,
	CASE
		WHEN p_id IS NULL THEN "Root"
		WHEN id IN (SELECT p_id FROM Tree WHERE p_id IS NOT NULL) THEN "Inner"
		ELSE "Leaf" 
	END AS "Type"
FROM Tree
ORDER BY id
```

<br/>

## Using IF

```MySQL
SELECT id,
IF(p_id IS NULL, "Root", 
   IF(id IN (SELECT p_id FROM Tree WHERE p_id IS NOT NULL), "Inner", "Leaf")) AS "Type"
FROM Tree
ORDER BY id
```