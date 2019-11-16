# Questions

## Part-1 

1. You are a data engineer implementing a Lambda architecture on Microsoft Azure. You use an open-source big data solution to collect, 
process, and maintain data. The analytics data store performs poorly.
You must implement a solution that meets the following requirements:
    - Provide data warehousing
    - Reduce ongoing management activities
    - Deliver SQL query responses in less than one second You need to create an HDInsight cluster to meet the requirements.
  Which type of cluster should you create?

- Interactive Query
- Apache Hadoop
- Apache HBase
- Apache Spark :heavy_check_mark:

```
Explanation:
Lambda Architecture with Azure
Azure offers you a combination of following technologies to accelerate real-time big data analytics
    - Azure Cosmos DB, a globally distributed and multi-model database service.
    - Apache Spark for Azure HDInsight, a processing framework that runs large-scale data analytics
      applications.
    - Azure Cosmos DB change feed, which streams new data to the batch layer for HDInsight to process.
    - The Spark to Azure Cosmos DB Connector
```

 <img src="/images/Dumps-Simulation/1.Dumps-Simulation-Architecture.jpg">
 
```    
Note: Lambda architecture is a data-processing architecture designed to handle massive quantities of data by
taking advantage of both batch processing and stream processing methods, and minimizing the latency
involved in querying big data.

References: 
https://sqlwithmanoj.com/2018/02/16/what-is-lambda-architecture-and-what-azure-offers-with-its-new-cosmos-db/
```

2. You develop data engineering solutions for a company. The company has on-premises Microsoft SQL Server databases a multiple locations.
The company must intergate data with Microsoft Power BI and Microsoft Azure Logic Apps.
The solution must avoid single points of failure during conection and transfer to the cloud. The solution must also minimize latency.
You need to secure the transfer of data between on-premises databases and Microsoft Azure.
What should you do?

- Install a standalone on-premises Azure data gateway at each location
- Install an on-premises data gateway in personal mode at each location
- Install an Azure on-premises data gateway at primary location
- Install an Azure on-premises data gateway as a cluster at each location :heavy_check_mark:

```
Explanation:
You can create high availability clusters of On-premises data gateway installations, to ensure your organization
can access on-premises data resources used in Power BI reports and dashboards. 
Such clusters allow gateway administrators to group gateways to avoid single points of failure in accessing on-premises data
resources. The Power BI service always uses the primary gateway in the cluster, unless it’s not available. In
that case, the service switches to the next gateway in the cluster, and so on.

References:
https://docs.microsoft.com/en-us/power-bi/service-gateway-high-availability-clusters
```

3. You are a data architect. The data engineering team needs to configure a synchronization of data between an on-premises Microsoft SQL 
server database to Azure SQL Database.
Ad-hoc and reporting queries are being overutilized the on-premises production instance. The synchronization
process must:
    - Perform an initial data synchronization to Azure SQL Database with minimal downtime
    - Perform bi-directional data synchronization after initial synchronization

You need to implement this synchronization solution.
Which synchronization method should you use?

- transactional replication
- Data Migration Assistant (DMA)
- backup and restore
- SQL Server Agent job
- Azure SQL Data Sync :heavy_check_mark:

```
Explanation:
SQL Data Sync is a service built on Azure SQL Database that lets you synchronize the data you select bi-
directionally across multiple SQL databases and SQL Server instances.
With Data Sync, you can keep data synchronized between your on-premises databases and Azure SQL
databases to enable hybrid applications.
Compare Data Sync with Transactional Replication
```

<img src="/images/Dumps-Simulation/2.Dumps-Simulation-SQL-Data-Sync.jpg">

```
References:
https://docs.microsoft.com/en-us/azure/sql-database/sql-database-sync-data
```

4. An application will use Microsoft Azure Cosmos DB as its data solution. The application will use the Cassandra
API to support a column-based database type that uses containers to store items.
You need to provision Azure Cosmos DB. Which container name and item name should you use?  Each correct
answer presents part of the solutions.
NOTE: Each correct answer selection is worth one point.

- collection
- rows :heavy_check_mark:
- graph
- entities
- table :heavy_check_mark:

```
Explanation:
Depending on the choice of the API, an Azure Cosmos item can represent either a document in a collection,
a row in a table or a node/edge in a graph. The following table shows the mapping between API-specific entities
to an Azure Cosmos item:
```

<img src="/images/Dumps-Simulation/3.1.Dumps-Simulation-Cosmos.jpg">

```
An Azure Cosmos container is specialized into API-specific entities as follows:
```

<img src="/images/Dumps-Simulation/3.2.Dumps-Simulation-Cosmos.jpg">

```
References:
https://docs.microsoft.com/en-us/azure/cosmos-db/databases-containers-items
```

5. A company has a SaaS solution that uses Azure SQL Database with elastic pools. The solution contains a
dedicated database for each customer organization. Customer organizations have peak usage at different
periods during the year.
You need to implement the Azure SQL Database elastic pool to minimize cost.
Which option or options should you configure?

- Number of transactions only
- eDTUs per database only
- Number of databases only
- CPU usage only
- eDTUs and max data size :heavy_check_mark:

```
Explanation:
The best size for a pool depends on the aggregate resources needed for all databases in the pool. This
involves determining the following:
    - Maximum resources utilized by all databases in the pool (either maximum DTUs or maximum vCores
      depending on your choice of resourcing model).
    -Maximum storage bytes utilized by all databases in the pool.
    
Note: Elastic pools enable the developer to purchase resources for a pool shared by multiple databases to
accommodate unpredictable periods of usage by individual databases. You can configure resources for the
pool based either on the DTU-based purchasing model or the vCore-based purchasing model.

References:
https://docs.microsoft.com/en-us/azure/sql-database/sql-database-elastic-pool
```

#### Credits: [certification-questions](https://www.certification-questions.com)
