**(optional - alternative for "[[2 Create Dataset in PBI App]]")**

#### ETL Layer

This is Power Query in a browser.

Is based on Power Query technology:
- Connecting to a data source
- Cleaning and preparing the data
- Merging and combining files

Technologies:
- Power BI service (dataflows editor)
- Power BI Desktop
	- To add data sources
		- You lose the ability to add additional data sources (not if adding dataflow after other data sources)
	- To make additional changes
		- To make changes on dataset after publishing it in Power BI service

Benefits of using dataflows
- It makes it a lot easier for people to collaborate inside the same organization on those dataflows (changes in the cloud automatically flow down to datasets and reports that use those dataflows)

---

#### Add data sources
- [https://app.powerbi.com/home](https://app.powerbi.com/home) -> Workspaces -> select workspace -> New -> Dataflow
	- [[Define New Tables]]
	- [[Link Tables from other Dataflows]]
	- [[Import Model]]

Add more data sources
- Right click in the "Queries" panel -> New query -> more

Save & close -> Name: ... -> Save

---

Display steps for queries
- View -> Diagram view

---

#### Options only in browser Power Query

See available columns (and their data types) in queries 
- View -> Schema view

Create the same transformations as earlier
- Click on three dots on a query -> Append queries as new