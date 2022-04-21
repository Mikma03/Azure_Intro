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
