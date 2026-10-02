# EC2 - Compute (Elastic Compute Cloud)

## What is EC2?
Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the AWS Cloud. Using Amazon EC2 eliminates your need to invest in hardware up front, so you can develop and deploy applications faster.

## Key Concepts

- **AMI (Amazon Machine Image):** A template that contains a software configuration (for example, an operating system, an application server, and applications). You use an AMI to launch an instance.
- **Instance Types:** EC2 offers a wide selection of instance types optimized to fit different use cases. Instance types comprise varying combinations of CPU, memory, storage, and networking capacity (e.g., t2.micro, m5.large).
- **Key Pairs:** Used to securely connect to your EC2 instance. It consists of a public key that AWS stores, and a private key file that you store.
- **Security Groups:** Acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic. You define rules that allow specific ports and IP addresses.
- **EBS (Elastic Block Store):** Provides block level storage volumes for use with EC2 instances. They are essentially virtual hard drives that persist independently from the life of an instance.
- **Public vs Private IP:** 
  - **Public IP:** Accessible from the internet. Changes if the instance is stopped and started.
  - **Private IP:** Used for communication within the AWS network (VPC). Not accessible from the outside internet.
- **Instance Lifecycle:** 
  - **Pending:** The instance is booting up.
  - **Running:** The instance is ready and operational.
  - **Stopping/Stopped:** The instance is temporarily shut down (you aren't billed for compute).
  - **Terminated:** The instance is permanently deleted.

## Common Use Cases
- Hosting websites and web applications.
- Running background processing tasks or batch jobs.
- Testing and development environments.
- High-performance computing (HPC).
