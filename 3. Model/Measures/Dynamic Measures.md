Steps to create them: https://www.youtube.com/watch?v=s4jeX9EKON4

[https://www.youtube.com/watch?v=ROyVkQ9vTjc](https://www.youtube.com/watch?v=ROyVkQ9vTjc "https://www.youtube.com/watch?v=royvkq9vtjc")

```sql(dax)
VAR SelectedMeasure = SELECTEDMEASURE()
RETURN
    IF(
        SelectedMeasure < 1E4,
        FORMAT(SelectedMeasure, "0,0"),
        IF(
            SelectedMeasure < 1E6,
            FORMAT(SelectedMeasure / 1E3, "#,##0") & "K",
            FORMAT(SelectedMeasure / 1E6, "#,##0") & "M"
        )
    )
```

```sql(dax)
SWITCH(
    TRUE(),
    SELECTEDMEASURE() < 10000, FORMAT(SELECTEDMEASURE(), "#,0"),
    SELECTEDMEASURE() < 1000000, FORMAT(SELECTEDMEASURE() / 1000, "#,0") & "K",
    SELECTEDMEASURE() < 1000000000, FORMAT(SELECTEDMEASURE() / 1000000, "#,0") & "M"
)
```

Nedelujoče:
SWITCH(

    TRUE(),

    SELECTEDMEASURE() >= 1000000000, FORMAT(SELECTEDMEASURE() / 1000000, "#,0") & "M",

    SELECTEDMEASURE() >= 1000000, FORMAT(SELECTEDMEASURE() / 1000, "#,0") & "K",

    SELECTEDMEASURE() >= 0, FORMAT(SELECTEDMEASURE(), "#,0"),

    SELECTEDMEASURE() > -10000, FORMAT(SELECTEDMEASURE(), "#,0"),

    SELECTEDMEASURE() > -1000000, FORMAT(SELECTEDMEASURE() / 1000, "#,0") & "K"

)

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