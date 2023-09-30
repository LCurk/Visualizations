You create additional measures beside the general measures when developing analytics model in Power BI.

All measures should have the same granularity (isto stopnjo podrobnosti).

Calculation Items Formulas: https://learn.microsoft.com/en-us/analysis-services/tabular-models/calculation-groups?view=asallproducts-allversions
- Time Intelligence
- Averages

**Instructions: https://www.youtube.com/watch?v=vlnx7QUVYME**

Order calculation items: https://learn.microsoft.com/en-us/analysis-services/tabular-models/calculation-groups?view=asallproducts-allversions#ordering

?? https://dash-intel.com/powerbi/time_intelligence_functions_closingbalance.php


Alternative (**bad**) are Time Intelligence functions in DAX (separate for every measure): https://www.sqlbi.com/articles/time-intelligence-in-power-bi-desktop/


---

Slicer to filter all measures on page in PBI Desktop for last 24 hours, 2 years, etc.
1. Create Calculation Items
2. [[Testing Table]] to insert into slicer

---

One click import calculation groups with [[Tabular Editor 2]] and [[Tabular Editor 3]]:
- https://www.youtube.com/watch?v=5i5hUU3IhJc&ab_channel=HavensConsulting (če želiš znotraj PBI modela pod vsako mero dodati time intelligence funkcije z enim klikom (da za tem, ko vstaviš #C formulo, označiš mere, in poženeš zadevo - kreirano pod Wages) or
- https://www.youtube.com/watch?v=_j0iTUo2HT0&ab_channel=GuyinaCube (kreiraš time intelligence tabelo, ki jo pol filtriraš v filtrih na merah - https://github.com/bernatagulloesbrina/time-intelligence/blob/main/Time%20Intelligence%20Calculation%20Group%20Creation.csx) or 
- https://www.esbrina-ba.com/one-click-calculation-groups-for-your-toolbelt/
Advanced scripting: https://docs.tabulareditor.com/te2/Advanced-Scripting.html

---

#### LY Measures

MP količina LY = CALCULATE([MP količina], SAMEPERIODLASTYEAR('Datum'[Datum]))

MP količina IND on LY = DIVIDE ([MP količina], CALCULATE([MP količina], SAMEPERIODLASTYEAR('Datum'[Datum])), BLANK())

MP fakturna vrednost % from LY = DIVIDE ([MP fakturna vrednost], CALCULATE([MP fakturna vrednost], SAMEPERIODLASTYEAR('Datum'[Datum]))) – 1

MP fakturna vrednost DIFF on LY =  CALCULATE([MP fakturna vrednost]) - CALCULATE([MP fakturna vrednost], SAMEPERIODLASTYEAR('Datum'[Datum]))

---

#### LM Measures

MP fakturna vrednost LM = CALCULATE([MP fakturna vrednost], DATEADD('Datum'[Datum], - 1, MONTH))

MP fakturna vrednost IND on LM = DIVIDE ([MP fakturna vrednost], CALCULATE([MP fakturna vrednost], DATEADD('Datum'[Datum], - 1, MONTH)), BLANK())

MP fakturna vrednost % from LM = DIVIDE ([MP fakturna vrednost], CALCULATE([MP fakturna vrednost], DATEADD('Datum'[Datum], -1, MONTH))) – 1

MP fakturna vrednost DIFF on LM =  CALCULATE([MP fakturna vrednost]) - CALCULATE([MP fakturna vrednost], DATEADD('Datum'[Datum], - 1, MONTH))

---

#### LD Measures

MP fakturna vrednost LD = CALCULATE([MP fakturna vrednost], DATEADD('Datum'[Datum], - 1, DAY))

MP fakturna vrednost IND on LD = DIVIDE ([MP fakturna vrednost], CALCULATE([MP fakturna vrednost], DATEADD('Datum'[Datum], - 1, DAY)), BLANK())

MP fakturna vrednost % from LD = DIVIDE ([MP fakturna vrednost], CALCULATE([MP fakturna vrednost], DATEADD('Datum'[Datum], - 1, DAY))) – 1

MP fakturna vrednost DIFF on LD =  CALCULATE([MP fakturna vrednost]) - CALCULATE([MP fakturna vrednost], DATEADD('Datum'[Datum], - 1, DAY))

---

#### YTD Measures

...

---

#### Example

Primeri za količino / število, vrednost, rabat…

- DIFF on LY
    - Mera DIFF on LY = CALCULATE([osnovna mera])-CALCULATE([osnovna mera], SAMEPERIODLASTYEAR('Datum'[Datum]))
- IND LY
    - Mera IND LY = DIVIDE([osnovna mera],CALCULATE([osnovna mera], SAMEPERIODLASTYEAR('Datum'[Datum])))
- IND YTD FY LY
    - Mera IND YTD FY LY = DIVIDE(TOTALYTD([osnovna mera],'Datum'[Datum]),TOTALYTD([osnovna mera], SAMEPERIODLASTYEAR('Datum'[Datum])))
- IND YTD LY
    - Mera IND YTD LY = DIVIDE([mera YTD],[mera YTD LY])
- LY
    - Mera LY = CALCULATE([osnovna mera], SAMEPERIODLASTYEAR('Datum'[Datum]))
- YTD
    - Mera YTD =  
        VAR MaxDate = CALCULATE(MAX('_Mere - Področje'[DatumRacunaID]), ALL('_Mere - Področje'))

VAR TableYTD = CALCULATETABLE(DATESYTD(Datum[Datum]), FILTER(Datum, Datum[Datum] <= MaxDate))

RETURNTOTALYTD([Osnovna mera], TableYTD)

- YTD FY
    - Mera YTD FY = TOTALYTD([Osnovna mera], 'Datum'[Datum])
- YTD FY DIFF on LY
    - Mera YTD FY DIFF on LY = TOTALYTD([osnovna mera], 'Datum'[Datum]) - TOTALYTD([osnovna mera], SAMEPERIODLASTYEAR('Datum'[Datum]))
- YTD FY LY
    - Mera YTD FY LY = TOTALYTD([Osnovna mera], SAMEPERIODLASTYEAR('Datum'[Datum]))

- YTD DIFF on LY
    - Mera YTD DIFF on LY = [Mera YTD] - [Mera YTD LY]
- IND LTD LY
    - Mera YTD FY = TOTALYTD([Osnovna mera], 'Datum'[Datum])
- YTD LY
    - Mera YTD LY = VAR MaxDate = CALCULATE(MAX('_Mere - Področje'[DatumRacunaID]), ALL('_Mere - Področje'))

VAR TableYTD = CALCULATETABLE(DATESYTD(DATEADD(Datum[Datum], -1, YEAR)), FILTER(Datum, Datum[Datum] <= MaxDate))

RETURNTOTALYTD([Osnovna mera], TableYTD)

#### Business Areas

- Stanje ___ (e.g.: stock): only LY

Stocks
- ...

Sales
- ...