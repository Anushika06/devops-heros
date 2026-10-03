## VPC - Networking (Virtual Private Cloud)

### What is VPC?

A VPC is a private network in AWS where we can launch and manage our AWS resources.

### Main Components

- **CIDR:** Defines the IP address range of the VPC. Example: `10.0.0.0/16`
- **Subnets:** Divide the VPC into smaller networks. Usually, we have public and private subnets.
- **Route Tables:** Decide where the traffic from a subnet should go.
- **Internet Gateway:** Connects the VPC to the internet. Used by public subnets.
- **NAT Gateway:** Lets resources in a private subnet access the internet without allowing direct incoming internet traffic.
- **Security Groups:** Firewall attached to resources like EC2. They control incoming and outgoing traffic.
- **Network ACLs:** Firewall applied at the subnet level.

### Simple Structure

```text
VPC
├── Public Subnet → Internet Gateway → Internet
│
└── Private Subnet → NAT Gateway → Internet
```

**In simple terms:** VPC is the network, subnets divide it, route tables decide the path, gateways connect it to the internet, and security groups/NACLs control the traffic.