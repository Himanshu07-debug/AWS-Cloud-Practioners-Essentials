## EC2 Storage Access Overview

- **Amazon EC2**:
  - Provides access to CPU, memory, network, and storage.
  - Focus on storage access, particularly block-level storage.

### Block-Level Storage
- **Definition**:
  - A place to store files as a series of bytes stored in blocks on a disk.
  - Efficient storage type for applications like databases, enterprise software, or file systems.
  
- **Update Mechanism**:
  - Only updates the pieces of data that change, rather than rewriting the entire file.

### EC2 Instance Storage Types

- **Instance Store Volumes**:
  - **Description**: Local storage physically attached to the host of the EC2 instance.
  - **Characteristics**:
    - Acts like a normal hard drive.
    - **Temporary**: Data is deleted when the instance is stopped or terminated.
    - **Use Cases**: Suitable for temporary files, scratch data, and data that can be easily recreated.

- **Amazon Elastic Block Store (EBS)**:
  - **Description**: A service that allows you to create virtual hard drives (EBS volumes) that can be attached to EC2 instances.
  - **Characteristics**:
    - **Persistent Storage**: Data remains intact even when the EC2 instance is stopped and started.
    - **Customization**: Define the size, type, and configurations of the EBS volume as per the requirements.
    - **Snapshots**:
      - Allows taking incremental backups of data.
      - **Importance**: Regular snapshots ensure data can be restored in case of drive corruption.
  
- **Usage**:
  - Attach EBS volumes to EC2 instances.
  - Configure applications to write data to the EBS volume.


## Amazon Simple Storage Service (S3) Overview

- **Introduction**:
  - S3 is a simple and scalable storage service.
  - Ideal for storing various data types, such as receipts, images, spreadsheets, and more.

### Key Features

- **Data Storage**:
  - Stores data as objects within buckets.
  - **Buckets**: Think of them as directories where objects (files) are stored.
  - **Object Size**: Maximum upload size is 5 terabytes.

- **Versioning**:
  - Protects objects from accidental deletion by retaining previous versions.

- **Permissions**:
  - You can set permissions to control who can view or access objects.

### Storage Classes

- **S3 Standard**:
  - Designed for frequently accessed data.
  - **Durability**: 11 nines (99.999999999%) durability, meaning a high likelihood that data remains intact for a year.
  - Data is stored across at least three facilities, ensuring high availability.

- **S3 Infrequent Access (S3-IA)**:
  - For data that is accessed less frequently but still requires quick access when needed.
  - Ideal for backups, disaster recovery, and long-term storage.

- **Amazon S3 Glacier**:
  - **Purpose**: Archiving data that doesn't require immediate retrieval.
  - **Vaults and Archives**: Store data in vaults, with options to lock the vault using policies like Write Once, Read Many (WORM).
  - **Retrieval**: Offers retrieval options ranging from minutes to hours.
    
- `Vault :`
    - a vault is a storage container used in the Amazon S3 Glacier service (formerly known as Amazon Glacier), which is designed for secure and durable storage of data that is infrequently accessed. Vaults are used to organize and manage archives, which are the actual data files or objects stored in Glacier.

- **Lifecycle Policies**:
  - Automates data movement between storage classes based on time.
  - Example: Keep data in S3 Standard for 90 days, then move to S3-IA for 30 days, and finally to S3 Glacier after 120 days.

### Additional Storage Classes

- **S3 Infrequent Access One Zone**:
  - A cost-effective option for infrequently accessed data stored in a single availability zone.
  
- **S3 Glacier Deep Archive**:
  - The lowest-cost storage option, ideal for data that is rarely accessed but needs to be retained for long periods.

### Additional Use Case

- **Static Website Hosting**:
  - Host static websites by uploading HTML and web assets into a bucket.
  - Easily accessible through the bucket's URL, making it a simple solution for web hosting needs.


### Amazon Elastic File System (EFS)
- **Purpose**: Scalable file storage for use with AWS Cloud services and on-premises resources.
- **Capacity**: Automatically scales up and down based on storage needs.
- **Use Cases**: Ideal for shared file systems that need to be accessed concurrently by multiple EC2 instances.
- **Key Features**:
  - Fully managed and **automatically scalable**.
  - Regional resource accessible by any EC2 instance in the same AWS Region.
  - Supports **NFS protocol** for Linux-based applications.
- **Advantages**:
  - No need to provision capacity in advance.
  - **High availability** and **durability** with data stored across multiple AZs.
  - Can be used for **shared data** and **distributed workloads**.


### Amazon Relational Database Service (RDS)
- **Purpose**: Managed relational database service.
- **Supported Engines**: MySQL, PostgreSQL, Oracle, Microsoft SQL Server, and Amazon Aurora.
- **Use Cases**: Ideal for applications that require complex queries and transactions.
- **Key Features**:
  - **Automated backups**, patching, and recovery.
  - Supports **multi-AZ deployments** for high availability.
  - Can scale **read capacity** using Read Replicas.
- **Advantages**:
  - Reduces the administrative burden of managing a database.
  - **Automated failover** and **point-in-time recovery**.
  - Aurora provides higher performance at a lower cost.

### Amazon DynamoDB
- **Purpose**: Serverless NoSQL database service.
- **Key Features**:
  - **Millisecond response times** and **automatic scaling**.
  - **Highly available** and **fault-tolerant** across AZs.
  - No need for predefined schema, allowing flexibility in data structure.
- **Use Cases**:
  - Applications with variable access patterns and scalability needs, such as gaming, IoT, and real-time data processing.
  - High-throughput applications with a need for low-latency data access.
- **Advantages**:
  - **Serverless**: No need to manage underlying infrastructure.
  - **Cost-effective**: Pay only for the resources consumed.
  - Ideal for applications that do not require complex queries.


## Comparison of RDS and DynamoDB

### Amazon RDS
- **Type**: Relational database service.
- **Data Model**: Structured data with predefined schemas.
- **Scaling**: Vertical scaling by increasing instance size or horizontal scaling using read replicas.
- **Use Cases**: Applications with complex queries, transactions, and strong consistency requirements.
- **Management**: AWS handles backups, patching, and maintenance.

### Amazon DynamoDB
- **Type**: NoSQL database service.
- **Data Model**: Unstructured or semi-structured data, schema-less.
- **Scaling**: Horizontal scaling with automatic partitioning.
- **Use Cases**: Applications requiring high throughput, flexible data models, and low-latency access.
- **Management**: Fully managed, serverless, with no need to manage infrastructure.


### Amazon Redshift 
- `Amazon Redshift` is a data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data.



## Amazon Database Migration Service (DMS)
- **Purpose**: Helps customers migrate existing databases onto AWS in a secure and easy fashion.
- **Functionality**: Migrates data between a source and a target database while keeping the source database fully operational during the migration to minimize downtime.
- **Key Features**:
  - Supports both **homogeneous** and **heterogeneous** migrations.
  - Can migrate on-premises databases, databases running on Amazon EC2, or Amazon RDS databases to other AWS databases.
  - Continuous replication is available for disaster recovery or geographic separation.
  - Use cases include development and test database migrations, database consolidation, and continuous database replication.

### Homogeneous Migrations
- **Definition**: Migrations where the source and target databases are of the same type.
- **Examples**:
  - MySQL to Amazon RDS for MySQL
  - Microsoft SQL Server to Amazon RDS for SQL Server
  - Oracle to Amazon RDS for Oracle
- **Process**: Fairly straightforward since schema structures, data types, and database code are compatible between source and target.
- **Operation**: Create a migration task with connections to the source and target databases, then start the migration with a click of a button.

### Heterogeneous Migrations
- **Definition**: Migrations where the source and target databases are of different types.
- **Steps**:
  1. Use the **AWS Schema Conversion Tool** to convert the source schema and code to match the target database.
  2. Use **DMS** to migrate data from the source database to the target database.

### Additional Use Cases for DMS
- **Development and Test Migrations**: Migrate a copy of your production database to your dev or test environments, either once-off or continuously.
- **Database Consolidation**: Consolidate several databases into one central database.
- **Continuous Replication**: Perform continuous data replication for disaster recovery or because of geographic separation.

## AWS Database Services

### Amazon DocumentDB
- **Purpose**: Document database service that supports MongoDB workloads.
- **Use Cases**: Best for working with document-oriented data.

### Amazon Neptune
- **Purpose**: Graph database service for highly connected datasets.
- **Use Cases**: Ideal for recommendation engines, fraud detection, and knowledge graphs.

### Amazon Quantum Ledger Database (Amazon QLDB)
- **Purpose**: Ledger database service to review a complete history of all the changes made to your application data.
- **Use Cases**: Ideal for applications requiring an immutable and cryptographically verifiable transaction log.

### Amazon Managed Blockchain
- **Purpose**: Create and manage blockchain networks using open-source frameworks.
- **Use Cases**: For applications that require distributed ledger systems where multiple parties can run transactions and share data without a central authority.

### Amazon ElastiCache
- **Purpose**: Adds caching layers on top of databases to improve read times of common requests.
- **Supported Data Stores**: Redis and Memcached.
- **Use Cases**: Ideal for applications that need quick data retrieval and can benefit from caching.

### Amazon DynamoDB Accelerator (DAX)
- **Purpose**: In-memory cache for DynamoDB.
- **Performance**: Improves response times from single-digit milliseconds to microseconds.
- **Use Cases**: Suitable for applications that require extremely fast read times from DynamoDB.

