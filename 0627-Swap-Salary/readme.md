```
Source : https://leetcode.com/problems/swap-salary/
Author : liuyubobobo
Time   : 2022-04-15
```

<br/>

## Using IF

```MySQL
UPDATE Salary
SET sex = IF(sex = 'm', 'f', 'm')
```

<br/>

## Using CASE

```MySQL
UPDATE Salary
SET sex = (
CASE 
    WHEN sex = 'm' THEN 'f'
    ELSE 'm'
END
)
```

<br/>

## Using XOR to swap

```MySQL
UPDATE Salary
SET sex = CHAR(ASCII('f') ^ ASCII('m') ^ ASCII(sex))
```

same idea but use + and -:

```MySQL
UPDATE Salary
SET sex = CHAR(ASCII('f') + ASCII('m') - ASCII(sex))
```

