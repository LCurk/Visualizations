?? If users will not change anything inside PBI report in PBI service, it is recommended, to give to customers permissions only for app, not for workspace where those PBI files are located.

---

[https://app.powerbi.com/home](https://app.powerbi.com/home) -> Apps -> three dots on a created App -> Manage permissions -> Manage audiences

- Create one audience for users that can access all pages in PBI report
	- Audience
	- Click on the »eyes« icon to show or hide PBI files
	- Edit Audience (add users) -> Update app -> Update
	- Copy link -> send link to customer on email

- Create audience(s) for users that can access only a few pages in PBI report: [YT](https://www.youtube.com/watch?v=MII8NIF98RM)
	- Make sure you have followed these steps:
		1. [[2 Create Dataset in PBI App]] (part: "if Souce is PBI file")
		2. [[Get Data from PBI Dataset]] (you should create more PBI files)
			- 1st audience: PBI file with all pages
			- 2nd audience: PBI file with only a few pages
		3. [[2 Publish PBI Report in PBI App]]
	- Audience -> New Audience
	- Click on the »eyes« icon to show or hide PBI files
	- Edit Audience (add users) -> Update app -> Update
	- Copy link -> send link to customer on email

? Don't share links to PBI files to customers. Teach them to access PBI Workspace or PBI App through https://app.powerbi.com/.