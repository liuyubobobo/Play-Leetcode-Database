```
Source : https://leetcode.com/problems/big-countries/
Author : liuyubobobo
Time   : 2022-04-14
```

<br/>

## Using OR

```MySQL
SELECT name, population, area 

FROM World 

WHERE area >= 3000000 OR population >= 25000000
```

<br/>

## Using UNION (which is slower)

```MySQL
SELECT name, population, area 

FROM World 

WHERE area >= 3000000 

UNION

SELECT name, population, area 

FROM World 

WHERE population >= 25000000
```