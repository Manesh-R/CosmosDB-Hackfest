
# Lab1: Introduction to Cosmos DB
## 1.	Introduction to Azure Cosmos DB
### 1.1	Create Cosmos DB Account with SQL API
1.	**Launch** a browser and **navigate** to https://portal.azure.com. **Login** with your Microsoft Azure credentials.<br/>
2.	To toggle show/hide the Portal menu options with icon, Click on the **Show Menu** button.<br/>     
<img src="images/showhide.jpg"/><br/>
3.	Click on the **New** icon in the Menu navigation bar.<br/>
<img src="images/new.jpg"/><br/>
4.	Type “**Cosmos db**” in the search box in the new blade that appears.<br/>
<img src="images/typeCosmosDB.jpg"/> <br/>
5.	Click on **Azure Cosmos DB** from the list that appears.<br/>
<img src="images/selectCosmosDB.jpg"/><br/>
6.	Click on Create in the **Azure Cosmos DB** blade.<br/>
<img src="images/cosmos_create.jpg"/><br/>
7.	Provide the following details in the Add directory blade.<br/>
    -	ID : Provide any unique name.
    -	API : **SQL** 
    -	Resource group : Select **Create new** and type the name of the new resource group to be created. <br/>
    Click on **Create**.<br/>
<img src="images/cosmosdbinfo.jpg"/><br/>
8.	After completion a notification will be raised as below.<br/>
<img src="images/cosmosdb_notification.jpg"/><br/>
### 1.2	Create new DB and collection
1.  **Launch** a browser and **navigate** to https://portal.azure.com. **Login** with your Microsoft Azure credentials.<br/>
2.  Click on the **Resource Group** icon on the **Menu navigation bar**.<br/>
<img src="images/rg.jpg"/><br/>
3.  Now in the **Resource Groups** blade that appear, select the created resource group for cosmos DB, (i.e, **cosmosdb-rg**).<br/>
<img src="images/cosmosrg.jpg"/><br/>
4.  Then click on the created Azure Cosmos DB account(i.e,cosmosdb321).<br/>
<img src="images/cosmosdb.jpg"/><br/>
5.	In the Azure Cosmos DB account blade that appear, Click on **Overview**.<br/>
<img src="images/cosmosdboverview.jpg"/><br/>
6.  Click on **+Add Collection**.<br/> 
<img src="images/selectAddCollection.jpg"/><br/>
7.  provide the following details in the Add Collection blade that appears.<br/>
    - Database id : Type a new database id
    - Collection id : Type a new collection id
    - Storage Capacity : **Fixed(10 GB)**
    - Throughput : **1000**<br/>
    Click on **OK**.<br/>
<img src="images/addcollectioninfo.jpg"/><br/>    
### 1.3	Load the Data in to the Cosmos DB.
#### 1.3.1	Access Windows VM and Launch Data migration tool.
1.  Download the data which we want to migrate into cosmos DB by clicking [here](http://jsonstudio.com/wp-content/uploads/2014/02/stocks.zip)<br/>
A zip file will download, extract and open the file to view the json data set.<br/>
2.  **Launch** your **data migration tool** by opening the **dtui.exe** application.<br/>
<img src="images/migrationtool.jpg"/><br/>   
3.  In the **DocumentDB Data Migration Tool** blade that appear, Click on **Next**.<br/>
<img src="images/mig-toolWelcome.jpg"/><br/>   
4.  In the source information page that appear, select Import from **JSON file(s)** and click on **Add Files**.<br/>
<img src="images/SourceInfo.jpg"/><br/>   
5.  Select the downloaded file, **stocks.json** and click on open.<br/>
<img src="images/importfiles.jpg"/><br/>   
6.  Then in the **source information** page, click on **Next** and a Target information page will appear.<br/><img src="images/SourceInfoNxt.jpg"/><br/>
7.  **Launch** a browser and **navigate** to https://portal.azure.com. **Login** with your Microsoft Azure credentials.<br/>
8.  Click on the **Resource Group** icon on the **Menu navigation bar**.<br/>
<img src="images/rg.jpg"/><br/>
9.  Now in the **Resource Groups** blade that appear, select the created resource group for cosmos DB, (i.e, **cosmosdb-rg**).<br/>
<img src="images/cosmosrg.jpg"/><br/>
10.  Then click on the created **Azure Cosmos DB account(i.e,cosmosdb321)**.<br/>
<img src="images/cosmosdb.jpg"/><br/>
11.  In the **Azure Cosmos DB account** blade, Click on **keys** menu under the **setting** tile.<br/>
<img src="images/keys.jpg"/><br/>   
12.  Then **copy** the **Primary Connection String** and paste the connection string in a notepad.<br/>
<img src="images/connString.jpg"/><br/>
13.  Now click on **Overview** menu in the **Azure Cosmos DB account** page and copy the newly created database name, i.e, mynewdb.<br/><img src="images/copyDBname.jpg"/><br/>
14.  Now open the notepad and after the connection string add the text **Database=mynewdb**.<br/>
<img src="images/notepad.jpg"/><br/>   
15.  Then go back to the **Target information** page of the Data migration tool and provide the following details.<br/>
       - Export to: **DocumentDB-Bulk import(Single partition collections)**.<br/>
       - Connection String: Copy the entire text from the notepad and paste it here.<br/>
    <img src="images/targetinfodb.jpg"/><br/>   
    After this Click on **Verify** button to verify the connection. Then a notification blade will pop-up which says **Successfully             connected to documentDB account**.In that notification blade click on **OK**. <br/>
    <img src="images/Notification.jpg"/><br/>   
       - Collections: Enter the name of the new collection, (i.e, **mynewcollection**).  
    After this Click on **Add** button to add the collection.<br/>
    <img src="images/targetinfocollection.jpg"/><br/>    
       - Collection throughput: Copy the collection **throughput** from the **overview** page of **Azure Cosmos DB account** and paste it here.<br/>
    Click on **Next** button.
    <img src="images/copythruput.jpg"/><br/>
    <img src="images/targetThruput.jpg"/><br/>
16.  Then an **advanced** page will appear, in that click on **Next**.
     <img src="images/advancedPage.jpg"/><br/>
17.  Then a Summary page will appear, in that click on **Import**.
     <img src="images/importtodb.jpg"/><br/>
18.  Now the import will start.It will take a couple of minutes to complete.
     <img src="images/exportStatus.jpg"/><br/>
### 1.4	Use Data Explorer to interact with collection
#### 1.4.1	Verify Data in Azure Portal
1.  **Launch** a browser and **navigate** to https://portal.azure.com. **Login** with your Microsoft Azure credentials.<br/>
2.  Click on the **Resource Group** icon on the **Menu navigation bar**.<br/>
<img src="images/rg.jpg"/><br/>
3.  Now in the **Resource Groups** blade that appear, select the created resource group for cosmos DB, (i.e, **cosmosdb-rg**).<br/>
<img src="images/cosmosrg.jpg"/><br/>
4.  Then click on the created **Azure Cosmos DB account(i.e,cosmosdb321)**.<br/>
<img src="images/cosmosdb.jpg"/><br/>
5.  In the **Azure Cosmos DB account** blade that appear, Click on **Data Explorer**.<br/>
<img src="images/dataexplorer.jpg"/><br/>
6.  In the **Data Explorer page**, Expand **mynewdb** to view the collections.<br/>
<img src="images/expanddb.jpg"/><br/>
7.  Then expand **mynewcollection**.<br/> 
<img src="images/expandCollection.jpg"/><br/>  
8.  Now click on **Documents** to view the data.<br/> 
<img src="images/cosmosdbDocuments.jpg"/><br/>  
9.  You can see the data by clicking the **IDs**.<br/>
<img src="images/selectID.jpg"/><br/>  
#### 1.4.2  Query data
1.  In the **Azure Cosmos DB account** blade that appear, Click on **Query Explorer**.<br/>
<img src="images/queryexplorer.jpg"/><br/>
2.  In the page that appear, select the our **Database(mynewdb)** and **Collection(mynewcollection)**.<br/>
<img src="images/QEslection.jpg"/><br/>
3.  Now type your query based on the requirement in the provided space and click on **Run Query**.<br/>
```
For example: SELECT * FROM c  WHERE c.Sector= "Financial"
```
<img src="images/queryrun.jpg"/><br/>
4.  Now we can see all the data with **Sector = Financial**<br/>
<img src="images/query_op.jpg"/><br/>
### 2.  Geo-Replication
#### 2.1   Create replication in multiple regions
1.  **Launch** a browser and **navigate** to https://portal.azure.com. **Login** with your Microsoft Azure credentials.<br/>
2.  Select the **Azure Cosmos DB account(i.e,cosmosdb321)**.<br/>
3.  In the Cosmos DB account page click on **Replicate data globally** tab under the **Settings** tile.<br/> 
<img src="images/replicate.jpg"/><br/>
4.  In the new page that appear, click on **Add new region** under **Read regions**.<br/>
<img src="images/addregion.jpg"/><br/>
5.  Now select the required **region** (say Central US) from the list and click on **OK**.<br/> 
<img src="images/regionok.jpg"/><br/>
6.  If you want to add more regions, click on Add new region again and select the required region and click on **Save**.
<img src="images/addregion2.jpg"/><br/>
<img src="images/replicationsave.jpg"/><br/>
