# DAX formula
MonthShort = 
	= UPPER(LEFT(FORMAT([Date], "mmm"), 1)) & RIGHT(FORMAT([Date], "mmm"), 2)

# Settings
Click on visual
- Visualizations -> Format visual -> Visual
- Slicer settings -> Options -> Style: Tile (Horizontal)

# Sort
By MonthNum:
- Data -> click on "MonthShort"
- Column tools -> "Sort one column by the contents of another" -> MonthNum

# Slicer example
Jan, Feb, ... , Dec