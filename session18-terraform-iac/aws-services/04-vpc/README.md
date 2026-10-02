# VPC - Networking (Virtual Private Cloud)

## What is VPC?
Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual network that you've defined. It closely resembles a traditional network that you'd operate in your own data center, with the benefits of using the scalable infrastructure of AWS.

## Key Concepts

- **CIDR (Classless Inter-Domain Routing):** A method for allocating IP addresses and IP routing. When you create a VPC, you assign an IPv4 CIDR block (e.g., 10.0.0.0/16) which determines the total number of IP addresses available in that network.
- **Subnets:** A range of IP addresses in your VPC. You divide a VPC into subnets to group resources based on security and operational needs.
- **Route Tables:** A set of rules, called routes, that are used to determine where network traffic from your subnet or gateway is directed.
- **Internet Gateway (IGW):** A horizontally scaled, redundant, and highly available VPC component that allows communication between your VPC and the internet.
- **NAT Gateway (Network Address Translation):** Allows instances in a private subnet to connect to services outside your VPC (like downloading updates from the internet) but prevents external services from initiating a connection with those instances.
- **Security Groups:** Stateful firewalls that operate at the instance level to control inbound and outbound traffic.
- **Network ACLs (Access Control Lists):** Stateless firewalls that operate at the subnet level to control inbound and outbound traffic.
- **Public vs Private Subnet:**
  - **Public Subnet:** A subnet whose route table directs internet-bound traffic to an Internet Gateway. Instances here can be accessed from the internet.
  - **Private Subnet:** A subnet without a direct route to the Internet Gateway. Instances here cannot be reached from the internet directly.
