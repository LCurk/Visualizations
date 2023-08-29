When you click on visual on a dashboard, you will be relocated to the page of the report where it originates.

Usage: monitoring the quality of data, threshold crossing by key performance indicators, etc.

1. Pin visuals to dashboard
	- Open report -> Edit -> click on visual you want to add to a dashboard -> select “pin” icon on a visual -> select existing dashboard or add new -> Go to dashboard

2. Create a card visual
	- Comparing two tables and find out which rows are missing

```dax
Employees Missing from Table2 = 
var MissingCount =  
    COUNTROWS(
        FILTER(
            'Table2',
            NOT CONTAINS(
                'Table2', 'Table2'[Column], 'Table'[Column]
            )
        )
    )
return

IF(
    ISBLANK(MissingCount), 0, MissingCount
)
```

3. Create automated data alerts on card visuals when your data on dashboard changes
	- Click on three dots on a card visual -> Manage alerts -> Add alert rule
		- If: Employees Missing from Table2 > 0
			- Condition: Above
			- Threshold: 0
			=> Alert on a card visual on a dashboard (“alert” icon)

4. Investigate why databases don’t match