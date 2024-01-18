Data Source Connection
- Power BI supports many on-premises data sources, and each source has its own requirements. You can use a gateway for a single data source or multiple data sources.
- Add a Data Source: https://learn.microsoft.com/en-us/power-bi/connect-data/service-gateway-data-sources#add-a-data-source

---

Different Data Sources:

#### Azure Blob Storage
- https://mystorageaccount.blob.core.windows.net/mycontainer/myblob
- Account name: mystorageaccount
- Account URL: https://mystorageaccount.blob.core.windows.net
- Authentication kind:
	- Shared Access Signature (SAS)
		- [[SAS Token]]
	- ...

Source: https://learn.microsoft.com/en-us/rest/api/storageservices/naming-and-referencing-containers--blobs--and-metadata#blob-names

#### SQL Server
- Gateway cluster name: ...
- Connection name: ...
- Connection type: SQL Server
- Server: ...
- Database: ...
Authentication
- Authentication Method: Windows
	- Username: ...
	- Password: ...
Privacy
- Privacy level: Organizational

Others: https://learn.microsoft.com/en-us/power-bi/connect-data/service-gateway-data-sources

#### File
