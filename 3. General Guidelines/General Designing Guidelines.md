First page(s):
- Overview, general information
- Main metrics with trend over time
- Less complex graphs (charts in main color)

Additional pages:
- More complex graphs (charts in main color + extremes in green and red)

---

Rule 1: [[Design for a target]]
Part of Rule 2: [[Hierarchical data]]
Rule 3: [[Keep it simple]]
Rule 8: [[Start from zero]]
Rule 6: [[Highlight the most relevant information]]
Rule 7: [[Be clear]]
Rule 9: [[Shorten the numbers]]
Rule 10: Show the context
Rule 12: [[Design dashboards, not reports]]
Rule 13: Show variations
Rule 14: [[Leave the noise off]]

Source:
- SqlBI Course ([[Dashboard Design Course]])





- 10: 
	- Visuals to use together:
		- Card with States (monthly) - glavna metrika
		- target/prev period (monthly)
			- z rdečo, če večje od glavne metrike
		- Sparkline (yearly by months)
		- Line chart (yearly by months)
- 13: 
	- Growth Rate (dodala mere)
	- lahko bi imeli "variance - absolute ali %"
		- če bi imeli target, bi ga rahko obarvali v rdeče, če ne bi dosegel targeta (dam primerjavo s prejšnjim mesecem?)
		- **Venera nam nikoli ni javljala planiranih vrednosti? če bi ga imeli, bi lahko tudi planiranje pokrivali, ker bi na bar chartu označli, do kje so prišli s prodajo v primerjavi s planirano**

- 14: 
	- ne delamo primerjav s targetom, ki ni dosegljiv
	- ne prikazujemo grafov, kjer ni povezav med vrednostmi
		- **če je povezava => Scatter Chart**
