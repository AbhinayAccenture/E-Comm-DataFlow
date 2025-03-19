*Purpose:

The purpose of this setup is to create an Azure Data Lake Storage Gen2 (ADLS Gen2) account to store raw e-commerce data (Amazon sales data). ADLS Gen2 will act as the source for data ingestion into Azure Synapse and Databricks for further processing and reporting.



*Steps to Set Up Data Lake Storage:

1. Create Azure Data Lake Storage (ADLS) Gen2

Sign in to the Azure Portal.
Go to Storage Accounts → + Create.
Configure the following settings:
Subscription: Select your subscription
Resource Group: Create a new or select an existing resource group
Storage Account Name: Use a unique name (e.g., ecommdatalake)
Region: Select the closest region
Performance: Standard
Replication: Locally-redundant storage (LRS)
Enable hierarchical namespace → Enabled (important for ADLS Gen2)
Click Review + Create → Create

2. Create a Container

In the newly created storage account, go to Containers → + Container
Name it raw-data
Set Public access level to Private
Click Create

3. Upload Sample Data

Open the raw-data container
Click Upload
Select the Amazon sales data files (CSV format)
Click Upload

4. Set Permissions

Go to Access keys → Copy the Connection string (for Databricks and Synapse)
Example ADLS Path:
https://<storage-account-name>.dfs.core.windows.net/raw-data/<filename>.csv



*Challenges & Suggestions:
⚠️ Permission Issues: Ensure that Databricks and Synapse have proper access to the container.
⚠️ Data Overwrite: Set proper overwrite settings if re-uploading data.
💡 Alternative: Use a SAS token if direct access via service principal is blocked.



*Outcome:
✅ Data Lake Storage is set up to store and ingest e-commerce data into Synapse and Databricks.
✅ Data is ready for processing and analysis.



Estimated Setup Time: 10–15 minutes
Skill Level: Beginner
Author: Abhinay Duggaraju