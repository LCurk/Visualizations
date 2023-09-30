It checks if the price is positive or negative.

#### Dimension

| **PriceSignID** | **PriceSign** |
|:---|:---|
| 1 | Positive |
| 2 | Negative |


#### Calculated Column in Fact
- If either "MPfakturna cena" or "MPplanska cena" is negative, it's categorized as 2 (indicating negativity).
- If both "MPfakturna cena" and "MPplanska cena" are non-negative, it's categorized as 1 (indicating non-negativity).

```dax
PriceSignID =
    IF(OR('_Mere - Zaloga Materialni Premiki'[MPfakturna cena] < 0, '_Mere - Zaloga Materialni Premiki'[MPplanska cena] < 0), 2, 1)
```