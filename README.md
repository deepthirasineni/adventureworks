### Table of Contents
1. Project Overview
2. Key Insights
3.  Project Architecture

* 3.1. Data Ingestion
* 3.2. Data Transformation
* 3.3. Data Loading

### 🔬 Project Overview

This is an end-to-end data engineering project on the Azure cloud. Where I did data ingestion from an on-premise SQL Server to Azure SQL Server and Azure Data Lake using Data Factory to transformation using Databricks and Spark, and loading to Synapse. Also, I used Azure Active Directory (AAD) and Azure Key Vault for data monitoring and governance purposes.

#### 💾 Dataset

The AdventureWorks dataset focuses on a fictional bicycle manufacturer named Adventure Works Cycles. It includes various data types related to the business, such as:

* **Sales:** Customer information, orders, products, pricing, and transactions.
* **Purchasing:** Vendor information, purchase orders, and receiving information.
* **Manufacturing:** Bill of materials, production information, and work orders.
* **Human Resources:** Employee information, job titles, salaries, and benefits.
* **Product Information:** Product descriptions, specifications, photos, pricing, and categories.

Tables are linked together using foreign keys, allowing you to explore relationships between different entities in the data.
For this project, I used the Lightweight (LT) data: a lightweight and pared-down version of the OLTP sample. 

**🎯 Project Goals**

Create the Azure SQL server and copy the database from the on-premise to the Azure SQL database. 
Establish a connection between the Azure SQL server and the Azure cloud.
Ingest tables into the Azure Data Lake.
Apply data cleaning and transformation using Azure Databricks.
Utilize Azure Synapse Analytics for loading clean data.
Implement Azure Active Directory (AAD) and Azure Key Vault for monitoring and governance.

**🕵️ Key Insights**

. 💸 Total Revenue by Product Category

Touring Bikes is the top 1 category generating revenue with 32% followed by Road Bikes with 26% and Mountain Bikes with 24%.

. 🌍 Sales by Country

N°1: The United Kingdom (UK) has the most total sales with 278 and $572,000 of total revenue.
N°2: The United States of America (USA) is second with total sales of 264 and $383,810 of total revenue.

. 🚻 Revenue by Gender

81% of the revenue is generated by Male customers
19% of the revenue is generated by Female customers
This can be explained by males having more interest in doing outdoor activities with the different categories of Bikes than females.


### 📝 Project Architecture

You can find the detailed information on the diagram below:
![adventure works](https://github.com/deepthirasineni/adventureworks/assets/62241395/6a013f9a-ee02-48f4-a412-9ab5017aee0d)




#### 📤 Data Ingestion

Connected the Azure SQL Server with Azure using Microsoft Integration Runtime.


Setup the Resource group with needed services (Key Vault, Storage Account, Data Factory, Databricks, Synapse Analytics)
<img width="1498" alt="resource-group" src="https://github.com/deepthirasineni/adventureworks/assets/62241395/48638481-80ff-41ca-9a90-46ec447a68f9">


Migrated the tables from the Azure SQL Server to Azure Data Lake Storage Gen2.
<img width="1507" alt="datafactory-pipeline" src="https://github.com/deepthirasineni/adventureworks/assets/62241395/3fe92d2f-be7b-44bb-bdb4-419993c37f8d">



#### ⚙️ Data Transformation

Mounted Azure Blob Storage to Databricks to retrieve raw data from the Data Lake.
Used Spark Cluster in Azure Databricks to clean and refine the raw data.
Saved the cleaned data in a Delta format; optimized for further analysis.

<img width="1503" alt="datalake" src="https://github.com/deepthirasineni/adventureworks/assets/62241395/83330ef4-6e87-40c4-898b-e57211247a09">


#### 📥 Data Loading

Used Azure Synapse Analytics to load the refined data efficiently.
Created SQL database and connected it to the data lake.
![synapse-workspace](https://github.com/deepthirasineni/adventureworks/assets/62241395/1b9af0b2-e904-4df0-8cab-b595c16e6139)



