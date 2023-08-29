**Change or trend over time.**

Display three Card with States for one measure:

1. [main metric] Act
	- Build visual
		- Measures: Act
		- Targets: Py
	- Format visual
		- States -> Comparison operator: <
		- Condition (Target): Act < Py => color "Act number" in red

2. Py
	- Build visual
		- Measures: Py

3. [difference between 2 numbers] Growth (%) = (Act - Py)/Py
	- Build visual
		- Measures: Growth (%)
	- Format visual
		- States -> Comparison operator: <
		- Condition 1: Growth (%) < 0 => color "Growth (%) number" in red

3. [difference between 2 percents] Diff = Act - Py
	- Build visual
		- Measures: Diff
	- Format visual
		- States -> Comparison operator: <
		- Condition 1: Diff < 0 => color "Diff number" in red