Option 3 (with Variables and not adding columns) is recommended.
- Variables are useful for
	- Readability of the code.
	- Split of the execution into logical steps
	- Easier debugging of the code.
	- Better performance.
- Adding columns is not recommended because

Spremenljivka, ki jo ustvariš v eni meri, se lahko nanjo sklicuješ samo lokalno, v isti meri.

---

#### 1. Option: [[Function CALENDARAUTO]]
- Only column Date created
- Date hierarchy created
- Slow

Modeling -> New table
```dax
Calendar = CALENDARAUTO()
```

---
#### 2. Option: Fuction ADDCOLUMNS
- No date hierarchy created
- No sorting (add sort by column)
- Fast

**Short version:**
Modeling -> New table
```sql (dax)
Calendar = 
ADDCOLUMNS(
    CALENDAR(DATE(2017, 01, 01), DATE(2024, 12, 31)),
    "WeekDay", WEEKDAY([Date], 2),
    "WeekDayWord", LEFT(FORMAT([Date], "ddd"), 1),
    "WorkDay", SWITCH(WEEKDAY([Date], 2), 6, 0, 7, 0, 1),
    "YearMthDay", FORMAT([Date], "yyyymmdd"),
    "Day", FORMAT([Date], "d"),
    "MonthNum", FORMAT([Date], "mm"),
    "MonthShort", UPPER(LEFT(FORMAT([Date], "mmm"), 1)) & RIGHT(FORMAT([Date], "mmm"), 2),
    "MonthLong", FORMAT([Date], "mmmm"),
    "Year", FORMAT([Date], "yyyy"),
    "YearMth", FORMAT([Date], "yyyymm"),
    "WeekNum", (WEEKNUM([Date], 2) - 1)
)
```

**Long version:**
Modeling -> New table

- [ ] Dopolni na podlagi Short verzije #todo/laura 

---

#### 3. Option: [[Function GENERATE]] and [[Fuction ROW]]

Include: [[Function CALENDAR]]

**Short version:**
Modeling -> New table
```sql (dax)
Calendar 5 =
VAR BaseCalendar =
    CALENDAR ( DATE ( 2016, 1, 1 ), DATE ( 2018, 12, 31 ) )
RETURN
    GENERATE (
        BaseCalendar,
        VAR BaseDate = [Date]
        VAR YearDate = YEAR ( BaseDate )
        VAR MonthNumber = MONTH ( BaseDate )
        VAR MonthName = FORMAT ( BaseDate, "mmmm" )
        VAR YearMonthName = FORMAT ( BaseDate, "mmm yy" )
        VAR YearMonthNumber = YearDate * 12 + MonthNumber - 1
        RETURN ROW (
            "Day", BaseDate,
            "Year", YearDate,
            "Month Number", MonthNumber,
            "Month", MonthName,
            "Year Month Number", YearMonthNumber,
            "Year Month", YearMonthName
        )
    )
```


**Long version:**
Modeling -> New table

- [ ] Dopolni na podlagi Short verzije #todo/laura 