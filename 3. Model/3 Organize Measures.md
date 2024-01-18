1. Create a Table for Measures
Enter data -> Add new table

2. Create Measures

3. Format Measures
	- Power BI Desktop -> Measure tools
		- Number
			- Format: Decimal number
			- , (comma)
			- Decimal places: 0
		- %
			- Format: Percentage
			- , (comma)
			- Decimal places: 2

4. Organize measures in folders https://radacad.com/organize-power-bi-dax-measures-in-folders)
	- Add Display Folders
		- PBI Desktop -> Model view -> select a column, measure, or calculated column (you can select multiple items using Ctrl+Click) -> Properties -> Display Folder: ... (name it)

5. Create [[Time Intelligence Calculation Items]] with [[Tabular Editor]]

6. Export measure formulas from Power BI
	- Izvoz iz Power BI-ja: https://visualbi.com/blogs/microsoft/powerbi/exporting-measure-column-formulas-power-bi/ -> v Excelu odpreš JSON (Data -> Get Data -> From File -> From JSON)
	- Izvoz iz Tabularja: https://exceleratorbi.com.au/copy-measures-between-2-power-bi-files/, https://www.youtube.com/watch?v=iWcUa6x_JRY


V Tabular pod "C# Script" prilepiš to formulo -> Run
```
//SKRIPTA ZA IZVOZ LASTNOSTI OBJEKTOV
// Construct a list of all visible columns and measures:
var objects = Model.AllMeasures.Where(m => !m.IsHidden && !m.Table.IsHidden).Cast<ITabularNamedObject>()
      .Concat(Model.AllColumns.Where(c => !c.IsHidden && !c.Table.IsHidden));
 // Get their properties in TSV format (tabulator-separated):
var tsv = ExportProperties(objects,"Name,ObjectType,Parent,Description,FormatString,DataType,Expression");
 // (Optional) Output to screen (can then be copy-pasted into Excel):
tsv.Output();
 
// ...or save the TSV to a file:
//SaveFile("documentation.tsv", tsv);
 
// KOPIRAŠ V EXCEL ,SHRANIŠ KOT CSV, POIMENUJEŠ.
```
-> copy to clipboard -> prilepiš v Excel -> "\n", ki se nahaja v formulah, zamenjaš s presledkom, ker to pomeni, da je bil narejen presledek za koncem formule


Izvoz mere iz DAX Studio: https://www.youtube.com/watch?v=49rP-qEpQ98

---

[[Dynamic Measures]]