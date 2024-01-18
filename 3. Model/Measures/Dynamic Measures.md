Steps to create them: https://youtu.be/s4jeX9EKON4?si=-L6cPJjVrfIUE1iv&t=195

Click on a measure -> Measure tools -> Format: Dynamic -> Enter DAX formula in "Format":

```sql(dax)
SWITCH(
    TRUE(),
    ABS(SELECTEDMEASURE()) < 10, "0.00",
    ABS(SELECTEDMEASURE()) < 1000, "0",
    ABS(SELECTEDMEASURE()) < 1000000, "#,.0K",
    ABS(SELECTEDMEASURE()) < 1000000000, "#,,.0M",
    ABS(SELECTEDMEASURE()) >= 1000000000, "#,,,.0bn"
)
```

---

Custom numeric formats: https://learn.microsoft.com/en-us/dax/format-function-dax#custom-numeric-formats

| If you use       | The result is                                                                                        |
|------------------|------------------------------------------------------------------------------------------------------|
| One section only | The format expression applies to all values.                                                         |
| Two sections     | The first section applies to positive values and zeros, the second to negative values.               |
| Three sections   | The first section applies to positive values, the second to negative values, and the third to zeros. |

---

Custom numeric format characters: https://learn.microsoft.com/en-us/dax/format-function-dax#custom-numeric-format-characters


Positive value, Negative value in brackets, Null value:
"#,0;(-#,0);#,0"

Positive value, Negative value, Null value:
"#,0;-#,0;#,0"