# 05. DynamoDB & RDS - Database Services

## DynamoDB
- **NoSQL**: Fully managed, serverless, key-value NoSQL database.
- **Tables**: Collection of data.
- **Items**: Individual records within a table.
- **Attributes**: Data elements comprising an item.
- **Partition Key**: Primary key component used to distribute data across partitions.
- **Sort Key**: Optional secondary key component to sort items with the same partition key.
- **Use Cases**: High-traffic web apps, gaming, IoT.

## RDS
- **Relational Database**: Fully managed SQL database service.
- **Supported Engines**: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server.
- **DB Instances**: Isolated database environments in the cloud.
- **Security**: Controlled via VPC, Security Groups, IAM, and encryption.
- **Backups**: Automated backups and manual snapshots.
- **Multi-AZ**: Synchronous replication across Availability Zones for high availability.
- **Read Replicas**: Asynchronous replication for read-heavy workloads.
- **Use Cases**: ERP, CRM, traditional e-commerce applications.