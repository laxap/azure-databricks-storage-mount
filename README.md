# Mounting Azure storage account containers in Databricks

> Databricks recommends not to use mount points in a production setup for security reasons. These setup instructions here are provided as a quick solution for quickstart environments.

## Steps to complete before running the notebook
1. Search for "Microsoft Entra ID" in the Azure portal and select the corresponding service.
2. Select "Manage > App registrations" and list "All applications".
3. Add a new app registration, Account type "Single tenant", e.g. named "DatabricksEntraIdApp".
4. Select "Manage > Certificates & secrets".
5. Add new client secret to the app.
6. Copy and temporarily store the secret value. It will be displayed only right after the creation of the client secret.
7. Get "Application (client) ID" and "Directory (tenant) Id" of the app. See Overview.
8. Create an Azure Key Vault.
9. Add role "Key Vault Administrator" to your user.
10. Add secrets, see keys in the notebook.
11. Add Role "Key Vault Administrator" to app "AzureDatabricks".
12. Add Secret Scope in Databricks via https://YOUR-DATABRICKS-HOST/#secrets/createScope, get DNS Name (Vault URI) and Resource ID from the Azure Key Vault properties.
13. Add the created Microsoft Entra ID app as "Storage Blob Data Contributor" to the container(s).
14. Change the name of the storage account and the list of the containers in the notebook.

## Links to additional information
- https://learn.microsoft.com/en-us/azure/databricks/getting-started/connect-to-azure-storage
- https://learn.microsoft.com/en-us/answers/questions/1290398/not-able-to-create-secrete-in-azure-key-valut