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
2. Copy raw data from data source to Azure Storage (Data Lake Gen2) using Azure Data Factory
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
zrob screeny jak tworzysz storage account

- Create container

- Create two directories inside the container: one storing raw data and one storing transformed data

- Create Data Factory

- Create pipeline (data-ingestion)
Copy every file from GitHub to Data Lake Gen 2 

- Create DataBricks Service
Create compute, create notebook,
mount storage account to databricks - app registration (create app), 
application client ID - 
Directory tenant ID -
SecretKey - (Create client secret)

provide permissions

- Create KeyVault

- Databricks trasnformation
load files, column name, change data types etc.

- Create Synapse analytics workspace
Lake Database

- Save As Images and add to PowerBI

-----------------------------------------------------------------------------------------
## Summary
During this project I found meaningful insides that gave me information about sport teams and their performance. Simultaneously I have learnt a lot about AWS, as well as practiced SQL queries!

## Authors

- [@Szymon Poparda](https://www.linkedin.com/in/szymon-poparda-02b96a248/)






