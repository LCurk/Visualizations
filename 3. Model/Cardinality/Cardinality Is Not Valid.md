IF cardinality isnt valid for relationship:
	- Povezava Transaction ID v fact tabeli z dimenzijsko tabelo bi mogla bit many to one, ampak ni prijelo. Zakaj?  - Duplicate table, lower case (replace š with s (in se za ž in č), remove duplicates, replace value / IF (SP LOKA or HOFER => ... ) (vse kar spada pod Grocery Čr, preimenuj v Grocery Čr, da bos potem iz tega nardila en condition - enako za shoping trgovine za obleke), remove duplicates, blanks, errors, nulls
		- Remove Duplicated from Part Number column
		- Remove Empty from Part Number Column
		- Remove Blanks from Part Number Column
		- Remove Errors from Part Number Column
	- Additional: https://learn.microsoft.com/en-us/power-bi/transform-model/desktop-many-to-many-relationships
- concentrate 2 columns: https://zebrabi.com/guide/how-to-concatenate-two-columns-in-power-bi/