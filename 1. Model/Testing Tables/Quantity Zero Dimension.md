It checks if different quantities are equal to zero or not.

#### Dimenzija

| **ReceiptOrIssueID** | **ReceiptOrIssue** |
|:---|:----:|
| 1 | Receipt |
| 2 | Issue |


#### Calculated Column in Fact
- If the received quantity = 0, it assigns a value of 2.
- It checks if the issued quantity = 0, it assigns a value of 1.
- If neither of the above conditions is met, it assigns a value of 0.

```dax
ReceiptOrIssueID = 
    IF
    (
        '_Mere - Zaloga Materialni Premiki'[MPsprejem količina] = 0,
        2,
        IF
        (
            '_Mere - Zaloga Materialni Premiki'[MPizdaja količina] = 0,
            1,
            0
        )
    )
```

