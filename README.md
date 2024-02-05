# Olympic_Analysis_Azure

In this project I'm going to use Git, as well as Azure Cloud (Azure Data Factory, Data Lake Gen 2, Azure Synapse Analytics, Azure Databricks etc.) to build the data pipeline in order to Extract, Transform and Load (ETL) the data from 2021 Olympics in Tokyo.

-----------------------------------------------------------------------------------------

## Built With
1. Data Source - 2021 Olympics in Tokyo dataset (from GitHub)

2. Data Extraction - Git Bash

3. Data Integration - Azure Data Factory

4. Raw Data Store - Azure Data Lake Gen2

5. Data Transformation - Azure DataBricks (PySpark)

6. Transformed Data - Azure Data Lake Gen2

7. Analytics - Azure Synapse Analytics

8. Visualization - PowerBI

![](images/icons1withpowerbi.png)

-----------------------------------------------------------------------------------------

## Scenario
1. Extract Data using Git Bash
   
2. Copy raw data to Azure Storage (Data Lake Gen2) using Azure Data Factory
   
3. Perform data transformation using Databricks (PySpark)
   
4. Upload transofrmed data to Azure Storage (Data Lake Gen2)
   
5. Understand the data in Azure Synapse Analytics using SQL queries
  
6. Visualize insights using PowerBI

![](images/dashboard1_nopowerBI.png)

-----------------------------------------------------------------------------------------

## Data Source
The data for this project was provided by @darshilparmar on his GitHub (2021 Olympics in Tokyo)

In order to pull this data I used Git Bash:
1. I initialized new repository
![](images/finalgit1.png)

2. I cloned repository from GitHub using Git Bash
![](images/finalgit2.png)

3. Added and commited changes
![](images/finalgit3.png)
![](images/finalgit4.png)

So in the end I was provided with 5 .csv files (Athletes, Coaches, EntriesGender, Medals, Teams)

Example: First rows of 'Athletes' table

![](images/athletes_table.png)

4. After that I put this data on my private GitHub

![](images/finalgit5.png)

-----------------------------------------------------------------------------------------

## Execution
- Create Storage Account and Resource Group

- Create container inside the storage account

- Create two directories inside the container: one storing raw data and one storing transformed data

- Create Data Factory
Create pipeline, which will copy the data from my private GitHub to Data Lake Gen2
Source:
GitHub repository

Sink:
ADLS (Azure Data Lake Storage) in the Storage Account

Create Linked Service

Now I just repeated the same process for the rest of my data

- Create DataBricks Service
Create compute -

Create Notebook - 

App Registration -

Configs - 

Put Sensitive Data into the keyvault - 
*I faced error: "The operation is not allowed by RBAC. If role assignments were recently changed, please wait several minutes for role assignments to become effective." Solution was to assign Key Vault Secrets Officer role to my account

Now I could create a secrets

Create Secret Scope in databricks
*Get URL from Microsoft documentation
*Paste it with Databricks instance name
*Took me to this page:

*I provided neccesary information
*Used this in notebook
*Opened documentation
*I faced an error: "Status code 403: Caller is not authorized to perform action on resource"
Solution was to assign 'Key Vault Secret User' role
*Now I could access my secrets
*I also configured databricks to access neccesaryy files
*I faced an error: "This request is not authorized to perform this operation using this permission."
Solution was to assign 'Storage Blob Data Contributor' role on my container to myself
*Now I got access to my container

*I started laoding my data
Databricks didnt include header, so i had to fix it
my data had headers so I set "header" as true

*I also noticed that 'entiresgender' table had string datatypes instead of integer, so  I fixed it
In order to do so I used built in AI assistant

* I also wanted to play a little bit with the databricks so I answered to quesitons:
# Find the top countries with the highest number of gold medals
# Calculate the average number of entries by gender for each discipline

*after the transformation I loaded the data into 'transformed-data' container

- Synapse Analytics
*I faced an error when creating Synapse workspace
"The Azure Synapse resource provider (Microsoft.Synapse) needs to be registered with the selected subscription."
Solution was to register Synapse Analytics inside subscription tab

*Now I could use Synapse Analytics

* I created new database and loaded my data there
* I ran a few SQL Queries to get insides from my data

* And synapse analytics automatically creates charts based on my query

 And with that I finished

-----------------------------------------------------------------------------------------
## Summary
During this project I found meaningful insides that gave me information about sport teams and their performance. Simultaneously I have learnt a lot about AWS, as well as practiced SQL queries!

## Authors

- [@Szymon Poparda](https://www.linkedin.com/in/szymon-poparda-02b96a248/)






