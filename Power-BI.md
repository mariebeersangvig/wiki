## Integrating with Microsoft Power BI

There are several pathways available to populate data into Power BI from Sesam.

# Client methods
1. Blank Query defined in PowerQuery M formula language.
2. Power BI Desktop Sesam Connector.

https://github.com/sesam-community/power-bi-client

3. Blank Query method to load datasets within Power BI Pro
It is also possible to use the Blank Query within the "dataflows" section of Power BI Pro web portal. This is possibly the easiest and most flexible method to load data into on a schedule from Sesam into Power BI.

Limits to storage in Power BI are outlined here:
https://docs.microsoft.com/en-us/power-bi/service-admin-manage-your-data-storage-in-power-bi

# Server (API) Methods
Sesam has a microservice available that allows a direct push integration from Sesam to Power BI via the Power BI REST API.

https://github.com/sesam-community/power-bi

This method is limited to datasets of 1 million entities by the Power BI REST API limits and the scehduling of the refresh of the dataset. Incremental is not available.