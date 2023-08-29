The goal of creating "filtering dimensions" is to check data accuracy across the data model.

Testing dimensions that should be created:
- Area: [[Material Stocks]] 
	- Sign
		- [[Price Sign Dimension]]
		- [[Quantity Sign Dimension]]
	- Availability
		- [[Price Availability Dimension]]
	- Zero
		- [[Price Zero Dimension]]
		- [[Quantity Zero Dimension]]
- Area: [[Finance]]
	- d
- Area: [[Sales]]
	- f

After creating dimensions, you should add a custom column to the dimension to implement condition written in a testing table.
- Usually used formulas: IF, OR, AND, etc.


Primeri:
- Vrednost/Količina (v primeru, da je cena=0, vseeno lahko upoštevaš količino.. v primeru da je cena negativna, se to ne upošteva.. če je količina=0 in cena pozitivna to ni smiselno vzet?)