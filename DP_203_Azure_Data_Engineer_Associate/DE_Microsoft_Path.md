# LEARNING PATH

<!-- TOC -->

- [LEARNING PATH](#learning-path)
- [Azure for the Data Engineer](#azure-for-the-data-engineer)
    - [Data abundance](#data-abundance)
    - [Difference between on-premises and cloud-based servers](#difference-between-on-premises-and-cloud-based-servers)
        - [On-premises environments](#on-premises-environments)
        - [Cloud environments](#cloud-environments)
    - [Understand job responsibilities](#understand-job-responsibilities)
        - [Change data processes](#change-data-processes)
    - [Explore data types](#explore-data-types)
        - [Structured data](#structured-data)
        - [Nonstructured data](#nonstructured-data)
    - [Understand data storage in Azure Storage](#understand-data-storage-in-azure-storage)
        - [When to use Blob storage](#when-to-use-blob-storage)
        - [Key features](#key-features)
        - [Data ingestion](#data-ingestion)
        - [Data security](#data-security)
    - [Understand data storage in Azure Data Lake Storage](#understand-data-storage-in-azure-data-lake-storage)
        - [Where to use Data Lake Storage Gen2](#where-to-use-data-lake-storage-gen2)
        - [Data ingestion](#data-ingestion)
        - [Queries](#queries)
        - [Data security](#data-security)
    - [Understand Azure Cosmos DB](#understand-azure-cosmos-db)
        - [When to use Azure Cosmos DB](#when-to-use-azure-cosmos-db)
        - [Key features](#key-features)
        - [Data ingestion](#data-ingestion)
        - [Queries](#queries)
        - [Data security](#data-security)
    - [Understand Azure SQL Database](#understand-azure-sql-database)
        - [When to use SQL Database](#when-to-use-sql-database)
        - [Key features](#key-features)
        - [Queries](#queries)
        - [Data security](#data-security)
    - [Understand Azure Synapse Analytics](#understand-azure-synapse-analytics)
        - [When to use Azure Synapse Analytics](#when-to-use-azure-synapse-analytics)
        - [Key features](#key-features)
        - [Ingesting and processing data](#ingesting-and-processing-data)
        - [Queries](#queries)
        - [Data security](#data-security)
    - [Understand Azure Stream Analytics](#understand-azure-stream-analytics)
        - [When to use Stream Analytics](#when-to-use-stream-analytics)
        - [Data ingestion](#data-ingestion)
        - [Data processing](#data-processing)
        - [Queries](#queries)
        - [Data security](#data-security)
    - [Understand Azure HDInsight](#understand-azure-hdinsight)
        - [Key features](#key-features)
        - [Ingesting data](#ingesting-data)
        - [Data processing](#data-processing)
        - [Queries](#queries)
        - [Data security](#data-security)
    - [Understand other Azure data services](#understand-other-azure-data-services)
        - [Databricks](#databricks)
        - [Data Factory](#data-factory)
        - [Azure Purview](#azure-purview)
    - [Identify job roles](#identify-job-roles)
        - [Data engineer](#data-engineer)
        - [Data scientist](#data-scientist)
        - [AI engineer](#ai-engineer)
        - [Role differences](#role-differences)
    - [Identify data engineering processes](#identify-data-engineering-processes)
        - [Move data around](#move-data-around)
        - [Extract](#extract)
        - [Transform](#transform)
        - [Load](#load)
        - [ETL tools](#etl-tools)
        - [Holistic data engineering](#holistic-data-engineering)
- [Store data in Azure](#store-data-in-azure)
    - [Choose a data storage approach in Azure](#choose-a-data-storage-approach-in-azure)
        - [Classify your data](#classify-your-data)
        - [Structured data](#structured-data)
        - [Semi-structured data](#semi-structured-data)
        - [Common formats](#common-formats)
            - [XML](#xml)
            - [JSON](#json)
            - [YAML](#yaml)
        - [Unstructured data](#unstructured-data)
    - [OLTP vs OLAP](#oltp-vs-olap)
    - [Azure Blob storage](#azure-blob-storage)
    - [Azure SQL Database](#azure-sql-database)

<!-- /TOC -->

# Azure for the Data Engineer

## Data abundance

Data forms include text, stream, audio, video, and metadata. Data can be structured, unstructured, or aggregated. For structured databases, data architects define the structure (schema) as they create the data storage in platform technologies such as Azure SQL Database and Azure SQL Data Warehouse. For unstructured (NoSQL) databases, each data element can have its own schema at query time. Data can be stored as a file in Azure Blob storage or as NoSQL data in Azure Cosmos DB or Azure HDInsight.

Data engineers must maintain data systems that are accurate, highly secure, and constantly available. The systems must comply with applicable regulations such as GDPR (General Data Protection Regulation) and industry standards such as PCI DSS (Payment Card Industry Data Security Standard).

## Difference between on-premises and cloud-based servers

### On-premises environments

**Computing environment**

On-premises environments require physical equipment to execute applications and services. This equipment includes physical servers, network infrastructure, and storage. The equipment must have power, cooling, and periodic maintenance by qualified personnel. A server needs at least one operating system (OS) installed. It might need more than one OS if the organization uses virtualization technology.

**Maintenance**

On-premises systems require maintenance for the hardware, firmware, drivers, BIOS, operating system, software, and antivirus software. Organizations try to reduce the cost of this maintenance where it makes sense.

**Scalability**

When administrators can no longer scale up a server, they can instead scale out their operations. To scale an on-premises server horizontally, server administrators add another server node to a cluster. Clustering uses either a hardware load balancer or a software load balancer to distribute incoming network requests to a node of the cluster.

**Availability**

High-availability systems must be available most of the time. Service-level agreements (SLAs) specify your organization's availability expectations.

System uptime can be expressed as three nines, four nines, or five nines. These expressions indicate system uptimes of 99.9 percent, 99.99 percent, or 99.999 percent. To calculate system uptime in terms of hours, multiply these percentages by the number of hours in a year (8,760).


**Total cost of ownership**

The term total cost of ownership (TCO) describes the final cost of owning a given technology. In on-premises systems, TCO includes the following costs:

Hardware
Software licensing
Labor (installation, upgrades, maintenance)
Datacenter overhead (power, telecommunications, building, heating and cooling)

### Cloud environments

**Computing environment**

Cloud computing environments provide the physical and logical infrastructure to host services, virtual servers, intelligent applications, and containers for their subscribers. Different from on-premises physical servers, cloud environments require no capital investment. Instead, an organization provisions service in the cloud and pays only for what it uses. 

On a cloud platform, storage is more generic. Diverse storage types include Azure Blob storage, Azure Files storage, and Azure Disk Storage.

**Maintenance**

In the cloud, Microsoft manages many operations to create a stable computing environment. This service is part of the Azure product benefit. Microsoft manages key infrastructure services such as physical hardware, computer networking, firewalls and network security, datacenter fault tolerance, compliance, and physical security of the buildings.

**Multilingual support**

Cloud systems often store data as a JSON file that includes the language code identifier (LCID). The LCID identifies the language that the data uses. Apps that process the data can use translation services such as the Bing Translator API to convert the data into an expected language when the data is consumed or as part of a process to prepare the data.

**Total cost of ownership**

Cloud systems like Azure track costs by subscriptions. A subscription can be based on usage that's measured in compute units, hours, or transactions. The cost includes hardware, software, disk storage, and labor. Because of economies of scale, an on-premises system can rarely compete with the cloud in terms of the measurement of the service usage.

**Lift and shift**

When moving to the cloud, many customers migrate from physical or virtualized on-premises servers to Azure Virtual Machines. This strategy is known as lift and shift. Server administrators lift and shift an application from a physical environment to Azure Virtual Machines without rearchitecting the application.

The lift-and-shift strategy provides immediate benefits. These benefits include higher availability, lower operational costs, and the ability to transfer workloads from one datacenter to another. The disadvantage is that the application can't take advantage of the many features available within Azure.

## Understand job responsibilities

SQL Server professionals generally work only with relational database systems. Data engineers also work with unstructured data and a wide variety of new data types, such as streaming data.

To master data engineering, you'll need to learn a new set of tools, architectures, and platforms. As a SQL Server professional, your primary data manipulation tool might be T-SQL. As a data engineer, you might use other technologies, like Azure HDInsight and Azure Cosmos DB. To manipulate the data in big-data systems, you might use languages such as HiveQL or Python.

### Change data processes

As a data engineer you'll extract raw data from a structured or unstructured data pool and migrate it to a staging data repository. Because the data source might have a different structure than the target destination, you'll transform the data from the source schema to the destination schema. This process is called transformation. You'll then load the transformed data into the data warehouse. Together, these steps form a process called extract, transform, and load (ETL).

A disadvantage of the ETL approach is that the transformation stage can take a long time. This stage can potentially tie up source system resources. This process is typically used for ingesting data from an on-premises database to an on-premises data warehouse.

An alternative approach is extract, load, and transform (ELT). In ELT, the data is immediately extracted and loaded into a large data repository, such as Azure Cosmos DB or Azure Data Lake Storage. This change in process reduces the resource contention on source systems. Data engineers can begin transforming the data as soon as the load is complete

ELT also has more architectural flexibility to support multiple transformations. For example, how the marketing department needs to transform the data can be different than how the operations department needs to transform that same data. This process is typically used for ingesting data from an on-premises database into the cloud.

## Explore data types

Azure provides many data platform technologies to meet the needs of common data varieties. It's worth reminding ourselves of the two broad types of data: structured data and nonstructured da

### Structured data

In relational database systems like Microsoft SQL Server, Azure SQL Database, and Azure SQL Data Warehouse, data structure is defined at design time. Data structure is designed in the form of tables. This means it's designed before any information is loaded into the system. The data structure includes the relational model, table structure, column width, and data types.

Relational systems react slowly to changes in data requirements because the structural database needs to change every time a data requirement changes. When new columns are added, you might need to bulk-update all existing records to populate the new column throughout the table.

Relational systems typically use a querying language such as Transact-SQL (T-SQL).

### Nonstructured data

Examples of nonstructured data include binary, audio, and image files. Nonstructured data is stored in nonrelational systems, commonly called unstructured or NoSQL systems. In nonrelational systems, the data structure isn't defined at design time, and data is typically loaded in its raw format. The data structure is defined only when the data is read. The difference in the definition point gives you flexibility to use the same source data for different outputs. Nonrelational systems can also support semistructured data such as JSON file formats.

The open-source world offers four types of NoSQL databases:

- Key-value store: Stores key-value pairs of data in a table structure.
- Document database: Stores documents that are tagged with metadata to aid document searches.
- Graph database: Finds relationships between data points by using a structure that's composed of vertices and edges.
- Column database: Stores data based on columns rather than rows. Columns can be defined at the query's runtime, allowing flexibility in the data that's returned performantly.

## Understand data storage in Azure Storage

Azure Storage accounts are the base storage type within Azure. Azure Storage offers a scalable object store for data objects and file system services in the cloud. It can also provide a messaging store for reliable messaging, or it can act as a NoSQL store.

Azure Storage offers four configuration options:

- Azure Blob: A scalable object store for text and binary data
- Azure Files: Managed file shares for cloud or on-premises deployments
- Azure Queue: A messaging store for reliable messaging between application components
- Azure Table: A NoSQL store for no-schema storage of structured data

You can use Azure Storage as the storage basis when you're provisioning a data platform technology such as Azure Data Lake Storage and HDInsight. But you can also provision Azure Storage for standalone use. For example, you provision an Azure Blob store either as standard storage in the form of magnetic disk storage or as premium storage in the form of solid-state drives (SSDs).

### When to use Blob storage
If you need to provision a data store that will store but not query data, your cheapest option is to set up a storage account as a Blob store. Blob storage works well with images and unstructured data, and it's the cheapest way to store data in Azure.

### Key features
Azure Storage accounts are scalable and secure, durable, and highly available. Azure handles your hardware maintenance, updates, and critical issues. It also provides REST APIs and SDKs for Azure Storage in various languages. Supported languages, runtime environments, and developer platforms include, .NET, Node.js, Java, Python, PHP, Ruby, and Go. Azure Storage also supports scripting in Azure PowerShell and the Azure CLI.

### Data ingestion
To ingest data into your system, use Azure Data Factory, Storage Explorer, the AzCopy tool, PowerShell, or Visual Studio. If you use the File Upload feature to import file sizes above 2 GB, use PowerShell or Visual Studio. AzCopy supports a maximum file size of 1 TB and automatically splits data files that exceed 200 GB.

### Data security
Azure Storage encrypts all data that's written to it. Azure Storage also provides you with fine-grained control over who has access to your data. You'll secure the data by using keys or shared access signatures.

Azure Resource Manager provides a permissions model that uses role-based access control (RBAC). Use this functionality to set permissions and assign roles to users, groups, or applications.

## Understand data storage in Azure Data Lake Storage

Azure Data Lake Storage is a Hadoop-compatible data repository that can store any size or type of data. This storage service is available as Generation 1 (Gen1) or Generation 2 (Gen2). Data Lake Storage Gen1 users don't have to upgrade to Gen2, but they forgo some benefits.

Data Lake Storage Gen2 users take advantage of Azure Blob storage, a hierarchical file system, and performance tuning that helps them process big-data analytics solutions. In Gen2, developers can access data through either the Blob API or the Data Lake file API. Gen2 can also act as a storage layer for a wide range of compute platforms, including Azure Databricks, Hadoop, and Azure HDInsight, but data doesn't need to be loaded into the platforms.

### Where to use Data Lake Storage Gen2

Data Lake Storage is designed to store massive amounts of data for big-data analytics. For example, Contoso Life Sciences is a cancer research center that analyzes petabytes of genetic data, patient data, and records of related sample data. Data Lake Storage Gen2 reduces computation times, making the research faster and less expensive.

The compute aspect that sits above this storage can vary. The aspect can include platforms like HDInsight, Hadoop, and Azure Databricks.

Key features
Here are the key features of Data Lake Storage:

- Unlimited scalability
- Hadoop compatibility
- Security support for both access control lists (ACLs)
- POSIX compliance
- An optimized Azure Blob File System (ABFS) driver that's designed for big-data analytics
- Zone-redundant storage
- Geo-redundant storage

### Data ingestion

To ingest data into your system, use Azure Data Factory, Apache Sqoop, Azure Storage Explorer, the AzCopy tool, PowerShell, or Visual Studio. To use the File Upload feature to import file sizes above 2 GB, use PowerShell or Visual Studio. AzCopy supports a maximum file size of 1 TB and automatically splits data files that exceed 200 GB.

### Queries

In Data Lake Storage Gen1, data engineers query data by using the U-SQL language. In Gen 2, use the Azure Blob Storage API or the Azure Data Lake System (ADLS) API.

### Data security
Because Data Lake Storage supports Azure Active Directory ACLs, security administrators can control data access by using the familiar Active Directory Security Groups. Role-based access control (RBAC) is available both in Gen1 and Gen2. Built-in security groups include ReadOnlyUsers, WriteAccessUsers, and FullAccessUsers.

Enable the firewall to limit traffic to only Azure services. Data Lake Storage automatically encrypts data at rest, protecting data privacy.

## Understand Azure Cosmos DB

Azure Cosmos DB is a globally distributed, multimodel database. You can deploy it by using several API models:

- SQL API
- MongoDB API
- Cassandra API
- Gremlin API
- Table API

Because of the multimodel architecture of Azure Cosmos DB, you benefit from each model's inherent capabilities. For example, you can use MongoDB for semistructured data, Cassandra for wide columns, or Gremlin for graph databases. When you move your data from SQL, MongoDB, or Cassandra to Azure Cosmos DB, applications that are built using the SQL, MongoDB, or Cassandra APIs will continue to operate.

### When to use Azure Cosmos DB

Deploy Azure Cosmos DB when you need a NoSQL database of the supported API model, at planet scale, and with low latency performance. Currently, Azure Cosmos DB supports five-nines uptime (99.999 percent). It can support response times below 10 ms when it's provisioned correctly.

### Key features

Azure Cosmos DB supports 99.999 percent uptime. You can invoke a regional failover by using programing or the Azure portal. An Azure Cosmos DB database will automatically fail over if there's a regional disaster.

By using multimaster replication, Azure Cosmos DB is guaranteed to achieve a response time of less than 10 ms for reads and writes.

To maintain the consistency of the data in Azure Cosmos DB, your engineering team should introduce a new set of consistency levels that address the unique challenges of planet-scale solutions. Consistency levels include strong, bounded staleness, session, consistent prefix, and eventual.

### Data ingestion

To ingest data into Azure Cosmos DB, use Azure Data Factory, create an application that writes data into Azure Cosmos DB through its API, upload JSON documents, or directly edit the document.

### Queries

As a data engineer, you can create stored procedures, triggers, and user-defined functions (UDFs). Or use the JavaScript query API. You'll also find other methods to query the other APIs within Azure Cosmos DB. For example, in the Data Explorer component, you can use the graph visualization panel.

### Data security

Azure Cosmos DB supports data encryption, IP firewall configurations, and access from virtual networks. Data is encrypted automatically. User authentication is based on tokens, and Azure Active Directory provides role-based security.

Azure Cosmos DB meets many security compliance certifications, including HIPAA, FedRAMP, SOX, and HITRUST.

## Understand Azure SQL Database

Azure SQL Database is a managed relational database service. It supports structures such as relational data and unstructured formats such as spatial and XML data. SQL Database provides online transaction processing (OLTP) that can scale on demand. You'll also find the comprehensive security and availability that you appreciate in Azure database services.

### When to use SQL Database

Use SQL Database when you need to scale up and scale down OLTP systems on demand. SQL Database is a good solution when your organization wants to take advantage of Azure security and availability features. Organizations that choose SQL Database also avoid the risks of capital expenditures and of increasing operational spending on complex on-premises systems.

SQL Database can be more flexible than an on-premises SQL Server solution because you can provision and configure it in minutes. Even more, SQL Database is backed up by the Azure service-level agreement (SLA).

### Key features

SQL Database delivers predictable performance for multiple resource types, service tiers, and compute sizes. Requiring almost no administration, it provides dynamic scalability with no downtime, built-in intelligent optimization, global scalability and availability, and advanced security options. These capabilities let you focus on rapid app development and on speeding up your time to market. You no longer have to devote precious time and resources to managing virtual machines and infrastructure.

Ingesting and processing data
SQL Database can ingest data through application integration from a wide range of developer SDKs. Supported programming languages, runtime environments, and developer platforms include, .NET, Node.js, Python, and Java. Beyond applications, you can also ingest data through Transact-SQL (T-SQL) techniques and from the movement of data using Azure Data Factory.

### Queries

Use T-SQL to query the contents of a SQL Database. This method benefits from a wide range of standard SQL features to filter, order, and project the data into the form you need.

### Data security

SQL Database provides a range of built-in security and compliance features. These features help your application meet security and compliance requirements like these:

- Advanced Threat Protection
- SQL Database auditing
- Data encryption
- Azure Active Directory authentication
- Multi-factor authentication
- Compliance certification

## Understand Azure Synapse Analytics

Azure Synapse Analytics is a cloud-based data platform that brings together enterprise data warehousing and Big Data analytics. It can process massive amounts of data and answer complex business questions with limitless scale.

### When to use Azure Synapse Analytics

Data loads can increase the processing time for on-premises data warehousing descriptive analytic solutions. Organizations that face this issue might look to a cloud-based alternative to reduce processing time and release business intelligence reports faster. But many organizations first consider scaling up on-premises servers. As this approach reaches its physical limits, they look for a solution on a petabyte scale that doesn't involve complex installations and configurations. The SQL Pools capability of Azure Synapse Analytics can meet this need.

The volume and variety of data that is being generated are providing opportunities to perform different types of analysis on the data. This can include techniques such as exploratory data analysis to identify initial patterns or meaning in the data. It can also include conducting predictive analytics for forecasting, or segmenting data. The Big Data Analytics capability of Azure Synapse Analytics will accommodate this.

### Key features

SQL Pools uses massively parallel processing (MPP) to quickly run queries across petabytes of data. Because the storage is separated from the compute nodes, you can scale the compute nodes independently to meet any demand at any time.

In Azure Synapse Analytics, the Data Movement Service (DMS) coordinates and transports data between compute nodes as necessary. But you can use a replicated table to reduce data movement and improve performance. Azure Synapse Analytics supports three types of distributed tables: hash, round-robin and replicated. Use these tables to tune performance.

Importantly, Azure Synapse Analytics can also pause and resume the compute layer. This means you pay only for the computation you use. This capability is useful in data warehousing.

### Ingesting and processing data

Azure Synapse Analytics uses the extract, load, and transform (ELT) approach for bulk data. SQL professionals are already familiar with bulk-copy tools such as bcp and the SQLBulkCopy API. Data engineers who work with Azure Synapse Analytics will soon learn how quickly PolyBase can load data.

PolyBase is a technology that removes complexity for data engineers. They take advantage of techniques for big-data ingestion and processing by offloading complex calculations to the cloud. Developers use PolyBase to apply stored procedures, labels, views, and SQL to their applications. You can also use Azure Data Factory to ingest and process data using PolyBase too.

### Queries

As a data engineer, you can use the familiar Transact-SQL to query the contents of Azure Synapse Analytics. This method takes advantage of a wide range of features, including the WHERE, ORDER BY, and GROUP BY clauses. Load data fast by using PolyBase with additional Transact-SQL constructs such as CREATE TABLE and SELECT.

### Data security

Azure Synapse Analytics supports both SQL Server authentication and Azure Active Directory. For high-security environments, set up multifactor authentication. From a data perspective, Azure Synapse Analytics supports security at the level of both columns and rows.

## Understand Azure Stream Analytics

Applications, sensors, monitoring devices, and gateways broadcast continuous event data known as data streams. Streaming data is high volume and has a lighter payload than nonstreaming systems.

Data engineers use Azure Stream Analytics to process streaming data and respond to data anomalies in real time. You can use Stream Analytics for Internet of Things (IoT) monitoring, web logs, remote patient monitoring, and point of sale (POS) systems.

<p align="center">
  <img src="https://docs.microsoft.com/en-us/learn/data-ai-cert/survey-the-azure-data-platform/media/8-streaming-analytics-framework.png"/>
</p> 

### When to use Stream Analytics

If your organization must respond to data events in real time or analyze large batches of data in a continuous time-bound stream, Stream Analytics is a good solution. Your organization must decide whether to work with streaming data or batch data.

In real time, data is ingested from applications or IoT devices and gateways into an event hub or IoT hub. The event hub or IoT hub then streams the data into Stream Analytics for real-time analysis.

Batch systems process groups of data that are stored in an Azure Blob store. They do this in a single job that runs at a predefined interval. Don't use batch systems for business intelligence systems that can't tolerate the predefined interval. For example, an autonomous vehicle can't wait for a batch system to adjust its driving. Similarly, a fraud-detection system must decline a questionable financial transaction in real time.

### Data ingestion

As a data engineer, set up data ingestion in Stream Analytics by configuring data inputs from first-class integration sources. These sources include Azure Event Hubs, Azure IoT Hub, and Azure Blob storage.

An IoT hub is the cloud gateway that connects IoT devices. IoT hubs gather data to drive business insights and automation.

Features in Azure IoT Hub enrich the relationship between your devices and your back-end systems. Bidirectional communication capabilities mean that while you receive data from devices, you can also send commands and policies back to devices. Take advantage of this ability, for example, to update properties or invoke device management actions. Azure IoT Hub can also authenticate access between the IoT device and the IoT hub.

Azure Event Hubs provides big-data streaming services. It's designed for high data throughput, allowing customers to send billions of requests per day. Event Hubs uses a partitioned consumer model to scale out your data stream. This service is integrated into the big-data and analytics services of Azure. These include Databricks, Stream Analytics, Azure Data Lake Storage, and HDInsight. Event Hubs provides authentication through a shared key.

You can use Azure Storage to store data before you process it in batches.

<p align="center">
  <img src="https://docs.microsoft.com/en-us/learn/data-ai-cert/survey-the-azure-data-platform/media/8-streaming-comparison.png"/>
</p>

### Data processing

To process streaming data, set up Stream Analytics jobs with input and output pipelines. Inputs are provided by Event Hubs, IoT Hubs, or Azure Storage. Stream Analytics can route job output to many storage systems. These systems include Azure Blob, Azure SQL Database, Azure Data Lake Storage, and Azure Cosmos DB.

After storing the data, run batch analytics in Azure HDInsight. Or send the output to a service like Event Hubs for consumption. Or use the Power BI streaming API to send the output to Power BI for real-time visualization.

### Queries

To define job transformations, use a simple, declarative Stream Analytics query language. The language should let you use simple SQL constructs to write complex temporal queries and analytics.

The Stream Analytics query language is consistent with the SQL language. If you're familiar with the SQL language, you can start creating jobs.

### Data security

Stream Analytics handles security at the transport layer between the device and Azure IoT Hub. Streaming data is generally discarded after the windowing operations finish. Event Hubs uses a shared key to secure the data transfer. If you want to store the data, your storage device will provide security.

## Understand Azure HDInsight

Azure HDInsight provides technologies to help you ingest, process, and analyze big data. It supports batch processing, data warehousing, IoT, and data science.

### Key features
HDInsight is a low-cost cloud solution. It includes Apache Hadoop, Spark, Kafka, HBase, Storm, and Interactive Query.

- Hadoop includes Apache Hive, HBase, Spark, and Kafka. Hadoop stores data in a file system (HDFS). Spark stores data in memory. This difference in storage makes Spark about 100 times faster.

- HBase is a NoSQL database built on Hadoop. It's commonly used for search engines. HBase offers automatic failover.
- Storm is a distributed real-time streaming analytics solution.
- Kafka is an open-source platform that's used to compose data pipelines. It offers message queue functionality, which allows users to publish or subscribe to real-time data streams.

### Ingesting data

As a data engineer, use Hive to run ETL operations on the data you're ingesting. Or orchestrate Hive queries in Azure Data Factory.

### Data processing

In Hadoop, use Java and Python to process big data. Mapper consumes and analyzes input data. It then emits tuples that Reducer can analyze. Reducer runs summary operations to create a smaller combined result set.

Spark processes streams by using Spark Streaming. For machine learning, use the 200 preloaded Anaconda libraries with Python. Use GraphX for graph computations.

Developers can remotely submit and monitor jobs from Spark. Storm supports common programming languages like Java, C#, and Python.

### Queries

Hadoop supports Pig and HiveQL languages. In Spark, data engineers use Spark SQL.

### Data security

Hadoop supports encryption, Secure Shell (SSH), shared access signatures, and Azure Active Directory security.

## Understand other Azure data services

To round out your understanding of offerings on the Azure data platform, consider Azure Databricks, Data Factory, and Azure Purview.

### Databricks

Databricks is a data analytics platform that's optimized for Azure. It provides one-click setup, streamlined workflows, and an interactive workspace for Spark-based applications.

Databricks adds capabilities to Apache Spark, including fully managed Spark clusters and an interactive workspace. You can use REST APIs to program clusters.

In Databricks notebooks, you'll use familiar programming tools such as R, Python, Scala, and SQL. Role-based security in Azure Active Directory and Databricks provides enterprise-grade security.

### Data Factory

Data Factory is a cloud-integration service. It orchestrates the movement of data between various data stores.

As a data engineer, you can create data-driven workflows in the cloud to orchestrate and automate data movement and data transformation. Use Data Factory to create and schedule data-driven workflows (called pipelines) that can ingest data from data stores.

Data Factory processes and transforms data by using compute services such as Azure HDInsight, Hadoop, Spark, and Azure Machine Learning. Publish output data to data stores such as Azure Synapse Analytics so that business intelligence applications can consume the data. Ultimately, you use Data Factory to organize raw data into meaningful data stores and data lakes so your organization can make better business decisions.

### Azure Purview
Azure Purview is a unified data governance service that helps you manage and govern your on-premises, multicloud, and software-as-a-service (SaaS) data. Easily create a holistic, up-to-date map of your data landscape with automated data discovery, sensitive data classification, and end-to-end data lineage. Empower data consumers to find valuable, trustworthy data.

## Identify job roles

### Data engineer
Data engineers provision and set up data platform technologies that are on-premises and in the cloud. They manage and secure the flow of structured and unstructured data from multiple sources. The data platforms they use can include relational databases, nonrelational databases, data streams, and file stores. Data engineers also ensure that data services securely and seamlessly integrate with other data platform technologies or application services such as Azure Cognitive Services, Azure Search, or even bots.

The Azure data engineer focuses on data-related tasks in Azure. Primary responsibilities include using services and tools to ingest, egress, and transform data from multiple sources. Azure data engineers collaborate with business stakeholders to identify and meet data requirements. They design and implement solutions. They also manage, monitor, and ensure the security and privacy of data to satisfy business needs.

The role of data engineer is different from the role of a database administrator. A data engineer's scope of work goes well beyond looking after a database and the server where it's hosted. Data engineers must also get, ingest, transform, validate, and clean up data to meet business requirements. This process is called data wrangling.

A data engineer adds tremendous value to both business intelligence and data science projects. Data wrangling can consume a lot of time. When the data engineer wrangles data, projects move more quickly because data scientists can focus on their own areas of work.

Both database administrators and business intelligence professionals can easily transition to a data engineer role. They just need to learn the tools and technology that are used to process large amounts of data.

### Data scientist
Data scientists perform advanced analytics to extract value from data. Their work can vary from descriptive analytics to predictive analytics. Descriptive analytics evaluate data through a process known as exploratory data analysis (EDA). Predictive analytics are used in machine learning to apply modeling techniques that can detect anomalies or patterns. These are an important part of forecast models.

Descriptive and predictive analytics are just one aspect of data scientists' work. Some data scientists might even work in the realms of deep learning, iteratively experimenting to solve a complex data problem by using customized algorithms.

Anecdotal evidence suggests that most of the work in a data science project is spent on data wrangling and feature engineering. Data scientists can speed up the experimentation process when data engineers use their skills to successfully wrangle data.

### AI engineer
AI engineers work with AI services such as Cognitive Services, Cognitive Search, and Bot Framework. Cognitive Services includes Computer Vision, Text Analytics, Bing Search, and Language Understanding (LUIS).

Rather than creating models, AI engineers apply the prebuilt capabilities of Cognitive Services APIs. AI engineers embed these capabilities within a new or existing application or bot. AI engineers rely on the expertise of data engineers to store information that's generated from AI.

For example, an AI engineer might be working on a Computer Vision application that processes images. This AI engineer would ask a data engineer to provision an Azure Cosmos DB instance to store the metadata and tags that the Computer Vision application generates.

### Role differences
The roles of the data engineer, AI engineer, and data scientist differ. Each role solves a different problem.

Data engineers primarily provision data stores. They make sure that massive amounts of data are securely and cost-effectively extracted, loaded, and transformed.

AI engineers add the intelligent capabilities of vision, voice, language, and knowledge to applications. To do this, they use the Cognitive Services offerings that are available out of the box.

When a Cognitive Services application reaches its capacity, AI engineers call on data scientists. Data scientists develop machine learning models and customize components for an AI engineer's application.

Each data-technology role is distinct, and each contributes an important part to digital transformation projects.

## Identify data engineering processes

Here are some of the tasks of an Azure data engineer:

- Design and develop data storage and data processing solutions for the enterprise.
- Set up and deploy cloud-based data services such as blob services, databases, and analytics.
- Secure the platform and the stored data. Make sure only the necessary users can access the data.
- Ensure business continuity in uncommon conditions by using techniques for high availability and disaster recovery.
- Monitor to ensure that the systems run properly and are cost-effective.

How a data engineer differs from a database administrator

The data engineer's role overlaps with the role of the database administrator (DBA) in terms of broad tasks. The differences are in scope and focus. Data engineers work with more than just databases, and they focus on cloud implementations rather than on-premises servers.

### Move data around
As a data engineer, you can transfer and move data in several ways. One way is to start an Extract, Transform, and Load (ETL) process.

Extraction sources can include databases, files, and streams. Each source has unique data formats that can be structured, semistructured, or unstructured. In Azure, data sources include Azure Cosmos DB, Azure Data Lake, files, and Azure Blob storage.

### Extract
During the extraction process, data engineers define the data and its source:

- Define the data source: Identify source details such as the resource group, subscription, and identity information such as a key or secret.

- Define the data: Identify the data to be extracted. Define data by using a database query, a set of files, or an Azure Blob storage name for blob storage.

### Transform
Define the data transformation: Data transformation operations can include splitting, combining, deriving, adding, removing, or pivoting columns. Map fields between the data source and the data destination. You might also need to aggregate or merge data.

### Load
Define the destination: During a load, many Azure destinations can accept data formatted as a JavaScript Object Notation (JSON), file, or blob. You might need to write code to interact with application APIs.

Azure Data Factory offers built-in support for Azure Functions. You'll also find support for many programming languages, including Node.js, .NET, Python, and Java. Although Extensible Markup Language (XML) was common in the past, most systems have migrated to JSON because of its flexibility as a semistructured data type.

Start the job: Test the ETL job in a development or test environment. Then migrate the job to a production environment to load the production system.

Monitor the job: ETL operations can involve many complex processes. Set up a proactive and reactive monitoring system to provide information when things go wrong. Set up logging according to the technology that will use it.

### ETL tools
As a data engineer, you'll use several tools for ETL. The most common tool is Azure Data Factory, which provides robust resources and nearly 100 enterprise connectors. Data Factory also allows you to transform data by using a wide variety of languages.

You might find that you also need a repository to maintain information about your organization's data sources and dictionaries. Azure Purview can store this information centrally.

Evolution from ETL
Azure has opened the way for technologies that can handle unstructured data at an unlimited scale. This change has shifted the paradigm for loading and transforming data from ETL to extract, load, and transform (ELT).

The benefit of ELT is that you can store data in its original format, be it JSON, XML, PDF, or images. In ELT, you define the data's structure during the transformation phase, so you can use the source data in multiple downstream systems.

In an ELT process, data is extracted and loaded in its native format. This change reduces the time required to load the data into a destination system. The change also limits resource contention on the data sources.

The steps for the ELT process are the same as for the ETL process. They just follow a different order.

Another process like ELT is called extract, load, transform, and load (ELTL). The difference with ELTL is that it has a final load into a destination system.

### Holistic data engineering
Organizations are changing their analysis types to incorporate predictive and preemptive analytics. Because of these changes, as a data engineer you should look at data projects holistically. Data professionals used to focus on ETL, but developments in data platform technologies lend themselves to an ELT approach.

Design data projects in phases that reflect the ELT approach:

- Source: Identify the source systems to extract from.
- Ingest: Identify the technology and method to load the data.
- Prepare: Identify the technology and method to transform or prepare the data.

Also consider the technologies you'll use to analyze and consume the data within the project. These are the next two phases of the process:

- Analyze: Identify the technology and method to analyze the data.
- Consume: Identify the technology and method to consume and present the data.

In traditional descriptive analytics projects, you might have transformed data in Azure Analysis Services and then used Power BI to consume the analyzed data. New AI technologies such as Azure Machine Learning services and Azure Synapse Analytics provide a wider range of technologies to automate some of the required analysis.

These project phases don't necessarily have to flow linearly. For example, because machine learning experimentation is iterative, the Analyze phase sometimes reveals issues such as missing source data or transformation steps. To get the results you need, you might need to repeat earlier phases.

To fully appreciate this process, let's examine it by using an example of high-level architecture.

# Store data in Azure

## Choose a data storage approach in Azure

### Classify your data

An online retail business has different types of data. Each type of data may benefit from a different storage solution.

Application data can be classified in one of three ways: structured, semi-structured, and unstructured. Here, you'll learn how to classify your data so that you can choose the appropriate storage solution.

### Structured data
Structured data, sometimes referred to as relational data, is data that adheres to a strict schema, so all of the data has the same fields or properties. The shared schema allows this type of data to be easily searched with query languages such as SQL (Structured Query Language). This capability makes this data style perfect for applications such as CRM systems, reservations, and inventory management.

Structured data is often stored in database tables with rows and columns with key columns to indicate how one row in a table relates to data in another row of another table. The below image shows data about students and classes with a relationship to grades that ties them together.

<p align="center">
  <img src="https://docs.microsoft.com/en-us/learn/modules/choose-storage-approach-in-azure/media/2-relational-db.png"/>
</p>


### Semi-structured data
Semi-structured data is less organized than structured data, and is not stored in a relational format, as the fields do not neatly fit into tables, rows, and columns. Semi-structured data contains tags that make the organization and hierarchy of the data apparent - for example, key/value pairs. Semi-structured data is also referred to as non-relational or NoSQL data. The expression and structure of the data in this style is defined by a serialization language.

For software developers, data serialization languages are important because they can be used to write data stored in memory to a file, sent to another system, parsed and read. The sender and receiver don’t need to know details about the other system, as long as the same serialization language is used, the data can be understood by both systems.

### Common formats
Today, there are three common serialization languages you're likely to encounter:

#### XML

XML, or extensible markup language, was one of the first data languages to receive widespread support. It's text-based, which makes it easily human and machine-readable. In addition, parsers for it can be found for almost all popular development platforms. XML allows you to express relationships and has standards for schema, transformation, and even displaying on the web.

Here's an example of a person with hobbies expressed in XML.

<Person Age="23">
    <FirstName>John</FirstName>
    <LastName>Smith</LastName>
    <Hobbies>
        <Hobby Type="Sports">Golf</Hobby>
        <Hobby Type="Leisure">Reading</Hobby>
        <Hobby Type="Leisure">Guitar</Hobby>
   </Hobbies>
</Person>

XML expresses the shape of the data using tags. These tags come in two forms: elements such as <FirstName> and attributes that can be expressed in text like Age="23". Elements can have child elements to express relationships - such as the <Hobbies> tag above which is expressing a collection of Hobby elements.

XML is flexible and can express complex data easily. However, it tends to be more verbose making it larger to store, process, or pass over a network. As a result, other formats have become more popular.

#### JSON

JSON – or JavaScript Object Notation, has a lightweight specification and relies on curly braces to indicate data structure. Compared to XML, it is less verbose and easier to read by humans. JSON is frequently used by web services to return data.

Here's the same person expressed in JSON.

{
    "firstName": "John",
    "lastName": "Doe",
    "age": "23",
    "hobbies": [
        { "type": "Sports", "value": "Golf" },
        { "type": "Leisure", "value": "Reading" },
        { "type": "Leisure", "value": "Guitar" }
    ]
}

Notice that this format isn't as formal as XML. It's closer to a key/value pair model than a formal data expression. As you might guess from the name, JavaScript has built-in support for this format - making it very popular for web development. Like XML, other languages have parsers you can use to work with this data format. The downside to JSON is that it tends to be more programmer-oriented making it harder for non-technical people to read and modify.

#### YAML

YAML – or YAML Ain’t Markup Language, is a relatively new data language that’s growing quickly in popularity in part due to its human-friendliness. The data structure is defined by line separation and indentation, and reduces the dependency on structural characters like parentheses, commas and brackets.

Here's the same person data expressed in YAML.

firstName: John
lastName: Doe
age: 23
hobbies:
    - type: Sports
      value: Golf
    - type: Leisure
      value: Reading
    - type: Leisure
      value: Guitar

This format is more readable than JSON and is often used for configuration files that need to be written by people but parsed by programs. However, YAML is the newest of these data formats and doesn't have as much support in programming languages as JSON and XML.


### Unstructured data
The organization of unstructured data is ambiguous. Unstructured data is often delivered in files, such as photos or videos. The video file itself may have an overall structure and come with semi-structured metadata, but the data that comprises the video itself is unstructured. Therefore, photos, videos, and other similar files are classified as unstructured data.

Examples of unstructured data include:

- Media files, such as photos, videos, and audio files
- Office files, such as Word documents
- Text files
- Log files

Now that you know the differences between each kind of data, let's look at the data sets used in an online retail business, and classify them.

## OLTP vs OLAP
Transactional databases are often called OLTP (Online Transaction Processing) systems. OLTP systems commonly support lots of users, have quick response times, and handle large volumes of data. They are also highly available (meaning they have very minimal downtime), and typically handle small or relatively simple transactions.

On the contrary, OLAP (Online Analytical Processing) systems commonly support fewer users, have longer response times, can be less available, and typically handle large and complex transactions.

The terms OLTP and OLAP aren't used as frequently as they used to be, but understanding them makes it easier to categorize the needs of your application.

Now that you're familiar with transactions, OLTP, and OLAP, let's walk through each of the data sets in the online retail scenario, and determine the need for transactions.

## Azure Blob storage
Azure Blob storage supports storing files such as photos and videos. It also works with Azure Content Delivery Network (CDN) by caching the most frequently used content and storing it on edge servers. Azure CDN reduces latency in serving up those images to your users.

By using Azure Blob storage, you can also move images from the hot storage tier to the cool or archive storage tier, to reduce costs and focus throughput on the most frequently viewed images and videos.

## Azure SQL Database
Business data will most likely be queried by business analysts, who are more likely to know SQL than any other query language. Azure SQL Database could be used as the solution by itself, but pairing it with Azure Analysis Services enables data analysts to create a semantic model over the data in SQL Database. The data analysts can then share it with business users, so that they only need to connect to the model from any business intelligence (BI) tool to immediately explore the data and gain insights.

## zure Cosmos DB
Azure Cosmos DB supports semi-structured data, or NoSQL data, by design. So, supporting new fields, such as the "Bluetooth-enabled" field or any new fields you need in the future, is a given with Azure Cosmos DB.

Azure Cosmos DB supports SQL for queries and every property is indexed by default. You can create queries so that your customers can filter on any property in the catalog.

Azure Cosmos DB is also ACID-compliant, so you can be assured that your transactions are completed according to those strict requirements.

As an added plus, Azure Cosmos DB also enables you to replicate your data anywhere in the world with the click of a button. So, if your e-commerce site has users concentrated in the US, France, and England, you can replicate your data to those data centers to reduce latency, as you've physically moved the data closer to your users.

Even with data replicated around the world, you can choose from one of five consistency levels. By choosing the right consistency level, you can determine the tradeoffs to make between consistency, availability, latency, and throughput. You can scale up to handle higher customer demand during peak shopping times, or scale down during slower times to conserve cost.