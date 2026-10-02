# DynamoDB & RDS - Database Services

## DynamoDB

**What is it?** DynamoDB is a fully managed, serverless, NoSQL key-value and document database designed to run high-performance applications at any scale.

- **NoSQL:** A non-relational database design. It doesn't use strict tables with foreign keys and SQL queries. It's highly flexible and scales horizontally.
- **Tables:** The top-level collection of data, similar to a table in a relational database.
- **Items:** A single record within a table, analogous to a row.
- **Attributes:** The individual data elements within an item, analogous to a column. Unlike SQL, items in the same DynamoDB table can have entirely different attributes.
- **Partition Key:** The primary key that uniquely identifies each item and dictates how data is distributed across physical partitions for fast access.
- **Sort Key:** An optional secondary key that lets you sort and query items that share the same partition key.
- **Use Cases:** Real-time bidding platforms, gaming leaderboards, shopping carts, and any app requiring single-digit millisecond latency at huge scale.

---

## RDS (Relational Database Service)

**What is it?** Amazon RDS is a managed service that makes it easy to set up, operate, and scale a relational database in the cloud.

- **Relational Database:** Stores data in structured tables with rows and columns, enforcing relationships between them. You query it using SQL.
- **Supported Engines:** Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle Database, and SQL Server.
- **DB Instances:** An isolated database environment running in the cloud. It contains one or more user-created databases.
- **Security:** Integrated with VPCs for network isolation, IAM for access control, and supports encryption at rest and in transit.
- **Backups:** Automated backups and manual snapshots are supported, allowing you to restore the database to a specific point in time.
- **Multi-AZ (Availability Zone):** A deployment option where RDS automatically provisions and maintains a synchronous standby replica in a different AZ for high availability and failover.
- **Read Replicas:** Asynchronous copies of your primary DB instance used to offload read-heavy workloads (like reporting or data analysis).
- **Use Cases:** Traditional enterprise applications, e-commerce platforms (managing inventory and transactions), ERP/CRM systems, and any scenario requiring complex SQL joins and ACID compliance.
