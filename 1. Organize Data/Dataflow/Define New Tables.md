Data sources:
- Excel
- Azure Blobs
- Azure SQL database

Next -> Transform data

---

#### Moving Queries from PBI Desktop to Dataflows

[https://app.powerbi.com/home](https://app.powerbi.com/home) -> Workspaces -> select workspace -> New -> Dataflow -> **Add new tables** -> Blank Query

**Import first table**
- PBI Desktop -> Home -> Transform data -> click on the first table -> Ctrl + C 
- Click into "Blank Query" in browser -> Ctrl + A -> Ctrl + V -> Next -> ([[4 Configure Connection]] if necessary)

**Import other tables**
- PBI Desktop -> Home -> Transform data -> click on the second table -> hold Shift -> click on the last table -> Ctrl + C
- Click unders first imported query in browser -> Ctrl + V -> ([[4 Configure Connection]] if necessary)
- Save & close