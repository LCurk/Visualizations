You create additional measures beside the general measures when developing analytics model in Power BI.

Import more measures at once in PBI:
- https://www.youtube.com/watch?v=3TdSp-lCGNk
- https://www.managility.co/bulk-measure-operations-in-power-bi/

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