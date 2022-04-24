```
Source : https://leetcode.com/problems/number-of-calls-between-two-persons/
Author : liuyubobobo
Time   : 2022-04-24
```

<br/>

## Using CASE

```MySQL
SELECT
    CASE 
        WHEN from_id < to_id THEN from_id
        ELSE to_id
    END AS person1,
    
    CASE 
        WHEN from_id < to_id THEN to_id
        ELSE from_id
    END AS person2,
    
    COUNT(duration) AS call_count,
    SUM(duration) AS total_duration
    
FROM Calls
GROUP BY person1, person2
```

<br/>

## Using IF

```MySQL
SELECT
    IF(from_id < to_id, from_id, to_id) AS person1,
    
    IF(from_id < to_id, to_id, from_id) AS person2,
    
    COUNT(duration) AS call_count,
    SUM(duration) AS total_duration
    
FROM Calls
GROUP BY person1, person2
```

<br/>

## Using GREATEST and LEAST

```MySQL
SELECT
    LEAST(from_id, to_id) AS person1,
    
    GREATEST(from_id, to_id) AS person2,
    
    COUNT(duration) AS call_count,
    SUM(duration) AS total_duration
    
FROM Calls
GROUP BY person1, person2
```


