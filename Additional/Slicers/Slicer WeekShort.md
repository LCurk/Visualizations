# DAX formula
WeekShort =
	= LEFT(FORMAT('Date'[Date], "ddd"), 2)

# Settings
Click on visual
- Visualizations -> Format visual -> Visual
- Slicer settings -> Options -> Style: Tile (Horizontal)

# Sort
By WeekNum:
- Data -> click on "WeekShort"
- Column tools -> "Sort one column by the contents of another" -> WeekNum

# Slicer example
Mo, Tu, ... , Su