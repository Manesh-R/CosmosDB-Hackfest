
# Lab1: Introduction to Cosmos DB
## 1.	Introduction to Azure Cosmos DB
### 1.1	Create Cosmos DB Account with SQL API
1.	**Launch** a browser and **navigate** to https://portal.azure.com. **Login** with your Microsoft Azure credentials.<br/>
2.	To toggle **show/hide** the Portal menu options with icon, Click on the Show Menu button.<br/>     
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
1.	Go to the created Cosmos DB by clicking on **Go to Resource** option in the notification bar.<br/>
<img src="images/gotoResource.jpg"/><br/>
2.	In the Azure Cosmos DB account blade that appear, Click on **Overview**.<br/>
<img src="images/cosmosdboverview.jpg"/><br/>
3.  Click on **+Add Collection**.<br/> 
<img src="images/selectAddCollection.jpg"/><br/>
4.  provide the following details in the Add Collection blade that appears.<br/>
    - Database id : Type a new database id
    - Collection id : Type a new collection id
    - Storage Capacity : **Fixed(10 GB)**
    - Throughput : **1000**<br/>
    Click on **OK**.<br/>
<img src="images/addcollectioninfo.jpg"/><br/>    
### 1.3	Load Data
#### 1.3.1	Access Windows VM and Launch Data migration tool.
1.  Download the data which we want to migrate into cosmos DB by clicking [here](http://portalcontent.blob.core.windows.net/samples/NutritionData.json)<br/>
2.  **Launch** your **data migration tool** by opening the **dtui.exe** application.<br/>
<img src="images/migrationtool.jpg"/><br/>   
3.  In the **DocumentDB Data Migration Tool** blade that appear, Click on **Next**.<br/>
<img src="images/mig-toolWelcome.jpg"/><br/>   
4.  In the source information page that appear, select Import from **JSON file(s)** and click on **Add Files**.<br/>
<img src="images/SourceInfo.jpg"/><br/>   
5.  Select the downloaded file, **NutritionData.json** and click on open.<br/>
<img src="images/importfiles.jpg"/><br/>   
6.  Then in the **source information** page, click on **Next** and a Target information page will appear.<br/><img src="images/SourceInfoNxt.jpg"/><br/>   
7.  Now go to your **Azure Cosmos DB account** and Click on **keys** menu under the **setting** tile.<br/><img src="images/keys.jpg"/><br/>   
8.  Then **copy** the **Primary Connection String** and paste the connection string in a notepad.<br/>
<img src="images/connString.jpg"/><br/>
9.  Now click on **Overview** menu in the **Azure Cosmos DB account** page and copy the newly created database name, i.e, mynewdb.<br/><img src="images/copyDBname.jpg"/><br/>
10.  Now open the notepad and after the connection string add the text **Database=mynewdb**.<br/>
<img src="images/notepad.jpg"/><br/>   
11.  Then go back to the **Target information** page of the Data migration tool and provide the following details.<br/>
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
12.  Then an **advanced** page will appear, in that click on **Next**.
     <img src="images/advancedPage.jpg"/><br/>
13.  Then a Summary page will appear, in that click on **Import**.
     <img src="images/importtodb.jpg"/><br/>
14.  Now the import will start.
     <img src="images/exportStatus.jpg"/><br/>





