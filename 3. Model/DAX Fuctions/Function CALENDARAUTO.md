It returns a table with a single column named "Date" that contains a contiguous set of dates. The range of dates is calculated automatically based on data in the model.
- fiscal_year_end_month: 1 - 12

```dax
CALENDARAUTO([fiscal_year_end_month])
```


#### Example

In this example, the MinDate and MaxDate in the data model are July 1, 2010 and June 30, 2011.
- `CALENDARAUTO()` will return all dates between January 1, 2010 and December 31, 2011.
- `CALENDARAUTO(3)` will return all dates between April 1, 2010 and March 31, 2012.
	- 3 is March.
	- April is 12 months back from March.