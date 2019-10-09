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

## Choosing Partition-Key

- A physical node can have 10 GB of information that means each Unique partition Key can have 10 GB of unique values.

