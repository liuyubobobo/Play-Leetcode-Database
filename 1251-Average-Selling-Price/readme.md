```
Source : https://leetcode.com/problems/average-selling-price/
Author : liuyubobobo
Time   : 2022-04-24
```

---

## Using ROUND

```MySQL
SELECT UnitsSold.product_id, 
    ROUND(SUM(Prices.price * UnitsSold.units) / SUM(UnitsSold.units), 2) AS average_price
FROM UnitsSold JOIN Prices
ON UnitsSold.product_id = Prices.product_id 
    AND UnitsSold.purchase_date BETWEEN Prices.start_date AND Prices.end_date
GROUP BY UnitsSold.product_id
```
