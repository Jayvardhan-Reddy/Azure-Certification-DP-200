# Azure-Certification-DP-200

Various modules and percentage involved in DP-200.

1) Data Storage - (20-30%)

2) Data Processing - (30-35%)
	- BigData Implementation
	- Developing Batch and Streaming solution
	- Integration solution
	- Implement Migration
	- Automate Datafactory pipelines

3) Data Security - (15-20%)
	- Managing source
	- Managing and configuring Data Authentication
	- Manage data policies and standards
	- Alerts

4) Monitoring Data Solutions - (10-15%)
	- Monitoring Data storing 
	- Database 
	- Data Processing

5) Troubleshooting Azure services - (10 - 15%)

## Pattern

<img src="images/1.Exam-Pattern.jpg">

- 7 MCP mandatory questions. (Cannot go back after selecting one answer)
- Case Study
	- Entire business and technical requirement
- Mixed Questions
	- Drag and drop

## Type of Data

<img src="images/2.Data-Types.jpg">

## Azure Storage

4 configurations options available includes

1) Azure Blob
	- Massive storage for Text and binary
  
2) Azure Files
    - Mange files or share for cloud or on premise deployment
    
3) Azure Kubes
    - Messaging store for reliable messaging between components
    
4) Azure Tables
    - A noSql stores for schema less storage of structured data

Azure Blob Usage
  - When we don’t have to query on the data stored
  - Less cost
  - Works well with images and unstructured format
  
## What service to use for Data?

<img src="images/3.Component-Usage-1.jpg">

<img src="images/4.Component-Usage-2.jpg">


## Architecture and usage of different Azure services

<img src="images/5.Architecture.jpg">

## Azure Databricks

- Apache Spark-based analytics platform
	- Simplifies the provisioning and collaboration of Apache Spark-based analytical solutions

- Enterprise Security
	- Utilizes the security capabilities of Azure
	
- Integration with other Cloud Services
	- Can integrate with variety of Azure data platform services and Power BI
	
## Azure HD-Insight

- Deploy cluster of Hadoop or Storm or Spark

## Azure Active Directory

- To guarantee security and manage person.
- Role  and user permission to Databricks and data lake.

## Reading Data in Azure Databricks

| SQL | DataFrame |
| :---: | :---: |
| SELECT col_1 FROM myTable | df.select(col("col_1")) |
| DESCRIBE myTable | df.printSchema() |
| SELECT * FROM myTable WHERE col_1 > 0 | df.filter(col("col_1") > 0) |
| ..GROUP BY col_2 | ..groupBy(col("col_2")) |
| ..ORDER BY col_2 | ..orderBy(col("col_2")) |
| ..WHERE year(col_3) > 1990 | ..filter(year(col("col_3"))) > 1990) |
| SELECT * FROM myTable LIMIT 10 | df.limit(10) |
| display(myTable)(text format) | df.show() |
| display(myTable)(html format) | display(df) |

## Performing ETL to populate a data model

<img src="images/6.ETL-DataModel.jpg">

## Transformations usually performed on a dataset

- Basic Transformations
	- Normalizing values
	- Missing/Null data
	- De-duplication
	- Pivoting Dataframes

- Advanced Transformations
	- User Defined functions
	- Joins and lookup tables
	- Multiple databases

## COSMOS-DB

Can Build Globally Distributed Databases with Cosmos DB

Azure Cosmos DB (NOSql)
- Scalability
- Performance
- Availability
- Programming Models 

## Request Units in Cosmos-DB

<img src="images/7.Request-Units.jpg">

Request Unit (RU) for a DB
- A single RU is equivalent to 1 KB of Get request
- Creation, deletion and insertion require additional processing costing more RU.
- RU can be changed at any point of time
- Value of RU can be set via [Capacity Planner](www.documentdb.com/capacityplanner)
	- Upload the sample JSON doc
	- Define no of documents
	- Minimum RU =  400
	- Maximum RU =  215 thousand (If we require more throughput then a ticket needs to raised in the Azure portal for it)

## Choosing Partition-Key

- Enable quick lookup of data
- Enable it to Autoscale when needed
- selection of right partition key is important during development process
- Partition key is the value used to organise your data into Logical divisions.
	- eg: In a Retail scenario
		- ProductID and UserID value as a partition key is a good choice.

Note:
 A physical node can have 10 GB of information that means each Unique partition Key can have 10 GB of unique values.
 
 
### Creating a Cosmos-DB

1. Click on resources and create it
2. Click on Data Explorer to create a Database name and the table
3. Use New Item tab to add the values to the table 
4. UDF can also be created as Stored procedures in Javascript.

We can also create the same using Azure CLI

```
az account list —output table	// Lists the set of Azure subscriptions that we have

Az account set —subscription “<subscription name>”

az  group list —out table	// List of resource groups 

export NAME=“<Azure Cosmos DB account name>”

export RESOURCE_GROUP=“<rgn>[sandbox resource group name]</rgn>”

Export LOCATION=“<location>”	// Data centre location

Export DB_NAME=“Products”

Az group create —name <name> —location <location>

Az cosmosdb create —name $NAME —kind GlobalDocumentDB —resource-group $RESOURCE_GROUP

Az cosmosdb database create —name $NAME —db-name $DB_NAME —resource-group $RESOURCE_GROUP

Az cosmosdb collection create —collection-name “Clothing“ —partition-key-path “/productId” —throughput 1000 - name $NAME —db-name $DB_NAME —resource-group $RESOURCE_GROUP
```

#### After creating a COSMOSDB
- Navigate to Data Explorer
- Click on New container and Database
- A container can have multiple Databases


## Cosmos DB fail over management

<img src="images/8.CosmosDB-Failove-Management.jpg">

## Cosmos DB Consistency Levels

| Consistency Level | Guarantees |
| :---: | :---: |
| Strong | Linearizability. Reads are guaranteed to return the most recent version of an item |
| Bounded Staleness | ConsistentPrefix. Reads lag behind writesby at most k prefixes or t interval. |
| Session | Consisten Prefix. Monotonic reads, monotonic writes, read-your-writes, write-follows-reads. |
| Consistent Prefix | Updates returned are some prefix of all the updates, with no gaps. |
| Eventual | Out of order reads. |

- Eventual consistency provide the weakest read consistency but offer lowest latency of both reads and writes. :bangbang: :triangular_flag_on_post:

Question related to setting up latency :bangbang: :triangular_flag_on_post:

What is the Latency I will have to use in order to provide the lower latency of reads and writes  :bangbang: :triangular_flag_on_post:
	- Eventual Consistency

 COSMOS-DB takes care of consistency of data when replicated  :bangbang: :triangular_flag_on_post:

## AZURE SQL DATABASE CONFIGURATION

- DTUs (Database Transaction Unit)
	- Combined measure of Compute, storage, and IO resources
- VCores
	- Enables you to configure resources independently
	- Greater control over compute and storage resources 
- SQL Elastic Pools
	- Relate to eDTUs.
	- Enable you to buy set of compute and storage resources that are shared among all the databases in the pool.	
	- Each database can use the resources they need.
- SQL Managed Instances
	- Creates a database with near 100% compatibility with the latest SQL server.
	- Useful for SQL Server  customers who would like t migrate on-premises servers instance in a “lift and shift” manner.

### shell.azure.com to start Azure shell

```
To connect to Database
jay@Azure:~$ az configure --defaults group=ms-dp-200 sql-server=jaysql01

jay@Azure:~$ az sql db list
O/P:
	

jay@Azure:~$ az sql db list | jq '[.[] | {name: .name}]'
O/P:
[
  {
    "name": "master"
  },
  {
    "name": "sqldbjay01"
  }
]

jay@Azure:~$ az sql db show --name sqldbjay01

az sql db show-connection-string --client sqlcmd --name sqldbjay01
O/P:
	"sqlcmd -S tcp:<servername>.database.windows.net,1433 -d sqldbjay01 -U <username> -P <password> -N -l 30"

"sqlcmd -S tcp:sqldbjay01.database.windows.net,1433 -d sqldbjay01 -U jay -P “******” -N -l 30"

SELECT name FEOM sys.tables; GO
```

SQL-DB does not take care of consistency of data when replicated, it needs to be done manually. :bangbang: :triangular_flag_on_post:

 ## SQL ELASTIC POOLS :bangbang: :triangular_flag_on_post:
 
 
