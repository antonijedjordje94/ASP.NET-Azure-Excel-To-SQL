---
services: blobs
platforms: c#
author: msonecode
---

# How to Import/Export Azure Excel file to/from Azure SQL Server in ASP.NET
This sample demonstrates how to import the worksheet Azure Excel file blob to DB on the Azure SQL Server and how to export from DB to Azure Excel blob.
## Running this sample

Do one of the following to start debugging:                                                                              
1. Click the Start Debugging button on the toolbar.                                                                                 
2. Click Start Debugging button in the Debug menu.                                                                                    
3. Press F5.    

- You will see the web page of this application.
![](Images/Empty.png)

- Then click button "Export to Excel".  
![](Images/Export.png)

- Click button "Import to DB" on the page.  
![](Images/Import.png)

- You can click the button "Clear Log" to clear the logs.  

## About the code

Before you build the project, make sure you have installed WindowsAzure.Storage package in the project.                                                 
The following steps can help you with the installation:                                                                                   
1. Open the solution CSWebAppAzureExcelImportExport.sln.                                                                            
2. Right click the project and select [Manage NuGet Packages...].                                                                                 
3. Search WindowsAzure.Storage at the Browse tab page. Find the right package and then install it.                                                      

You also need to set your Azure information in Helper.cs file:                                     

```cs
StorageCredentials cred = new StorageCredentials("[Your storage account name]", "[Your storage account key]");
CloudBlobContainer container = new CloudBlobContainer(new Uri("http://[Your storage account name].blob.core.windows.net/[Your container name] /"), cred);
string connectionStr = "Azure SQL Server Connection String";
```
Run CreateTable.sql in the SQLScripts folder on your Azure SQL Server DB to create test table and test data, or you can set your data table info first in Helper.cs file if you want to test your own data:                      

```cs
List<string> columns = new List<string>() { "{column1}", "{column2}", "{column3}"};
string tableName = "{table name}";
```

## More information
See more about this sample: <https://code.msdn.microsoft.com/How-to-ImportExport-Azure-0c858df9>                                            
For more information about Open XML, see <https://msdn.microsoft.com/en-us/library/office/bb456488.aspx>                                                        
About Azure SQL Database development, see <https://azure.microsoft.com/en-us/documentation/articles/sql-database-develop-overview/>                                    
To learn more about SqlBulkCopy class, see <https://msdn.microsoft.com/en-us/library/system.data.sqlclient.sqlbulkcopy(v=vs.110).aspx>
