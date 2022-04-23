```
Source : https://leetcode.com/problems/capital-gainloss/
Author : liuyubobobo
Time   : 2022-04-22
```

<br/>

## Using CASE

```MySQL
SELECT stock_name, 
SUM(
    CASE 
        WHEN operation = 'Sell' THEN price
        ELSE -price
    END
) AS capital_gain_loss
FROM Stocks
GROUP BY stock_name
```

<br/>

## Using IF

```MySQL
SELECT stock_name, SUM(IF(operation = 'Sell', price, -price)) AS capital_gain_loss
FROM Stocks
GROUP BY stock_name
```

