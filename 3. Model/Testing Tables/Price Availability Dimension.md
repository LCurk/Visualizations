It checks if the ...

#### Dimenzija

| **PriceAvailabilityID** | **PriceAvailability** |
|:---|:---|
| 1 | Only Invoice |
| 2 | Only Plan |
| 3 | Both |
| 4 | None |


#### Calculated Column in Fact
- If both "MPfakturna cena" and "MPplanska cena" are not equal to 0, it assigns a value of 3.
- If "MPfakturna cena" is not equal to 0 and "MPplanska cena" is equal to 0, it assigns a value of 1.
- If "MPfakturna cena" is equal to 0 and "MPplanska cena" is not equal to 0, it assigns a value of 2.
- If neither of the above conditions is met (both "MPfakturna cena" and "MPplanska cena" are equal to 0), it assigns a value of 4.

```dax
PriceAvailabilityID =
    VAR cena =
        IF
        (
            AND([MPfakturna cena] <> 0, [MPplanska cena] <> 0),
            3,
            IF
            (
                [MPfakturna cena] <> 0,
                1,
                IF
                (
                    [MPplanska cena] <> 0,
                    2,
                    4
                )
            )
        )
    RETURN
        cena
```

