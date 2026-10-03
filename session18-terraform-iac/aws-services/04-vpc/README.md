# **04. VPC - Networking**

## What is VPC?

**VPC (Virtual Private Cloud)** is a private network inside AWS where we can launch and manage resources such as EC2 instances, databases, and load balancers.

When creating a VPC, we define its IP address range and then divide it into smaller **subnets**.

---

## CIDR

**CIDR (Classless Inter-Domain Routing)** defines the IP address range available in the VPC or subnet.

Example:

```text
VPC: 10.0.0.0/16
```

The `/16` tells us how large the network is.

We can then divide it into smaller ranges:

```text
VPC:             10.0.0.0/16

Public Subnet:   10.0.1.0/24
Private Subnet:  10.0.2.0/24
```

---

## Subnets

A **subnet** is a smaller section of the VPC's IP address range.

We usually create:

- **Public subnet** → for resources that need internet-facing access.
- **Private subnet** → for resources that should not be directly accessible from the internet.

For example, a web server can be placed in a public subnet, while a database can be placed in a private subnet.

---

## Route Tables

A **route table** contains rules that decide where network traffic should go.

For example:

```text
Destination     Target
10.0.0.0/16     local
0.0.0.0/0       Internet Gateway
```

Here, `0.0.0.0/0` means any destination that isn't covered by another route should go to the Internet Gateway.

Each subnet is associated with a route table.

---

## Internet Gateway (IGW)

An **Internet Gateway** connects the VPC to the internet.

For a public subnet, the route table can contain:

```text
0.0.0.0/0 → Internet Gateway
```

This allows resources in that subnet to communicate with the internet, provided the resource also has the required public IP and security rules.

---

## NAT Gateway

A **NAT (Network Address Translation) Gateway** is mainly used by resources in a **private subnet** when they need to access the internet.

For example, a private EC2 instance might need to download software updates.

The traffic can go:

```text
Private EC2
     ↓
Private Route Table
     ↓
NAT Gateway
     ↓
Internet Gateway
     ↓
Internet
```

The important point is that the private EC2 can **initiate outbound connections**, but the internet cannot directly initiate a connection to that EC2 through the NAT Gateway.

A NAT Gateway is generally placed in a **public subnet**.

---

## Security Groups

A **Security Group (SG)** acts as a firewall for resources such as EC2 instances.

It controls:

- Inbound traffic
- Outbound traffic

Example:

```text
Allow SSH (22) from my IP
Allow HTTP (80) from anywhere
```

Security Groups are **stateful**, meaning if an incoming request is allowed, the response traffic is automatically allowed.

---

## Network ACLs

A **Network ACL (NACL)** is a firewall that works at the **subnet level**.

It controls:

- Inbound traffic
- Outbound traffic

Unlike Security Groups, NACLs are **stateless**, so inbound and outbound traffic rules are evaluated separately.

### Main difference

| Security Group | Network ACL |
|---|---|
| Works at resource level | Works at subnet level |
| Stateful | Stateless |
| Allows rules | Allows and denies rules |
| Applied to resources like EC2 | Applied to subnets |

---

## Public vs Private Subnet

### Public Subnet

A subnet is considered **public** when its route table has a route to an Internet Gateway.

```text
EC2
 ↓
Public Subnet
 ↓
Route Table
 ↓
Internet Gateway
 ↓
Internet
```

### Private Subnet

A private subnet does **not** have a direct route to an Internet Gateway.

If its resources need outbound internet access, they can use a NAT Gateway.

```text
EC2
 ↓
Private Subnet
 ↓
NAT Gateway
 ↓
Internet Gateway
 ↓
Internet
```

---

## Overall VPC Structure

```text
                    Internet
                       │
                       ▼
              Internet Gateway
                       │
        ┌──────────────┴──────────────┐
        │             VPC             │
        │          10.0.0.0/16        │
        │                             │
        │  Public Subnet              │
        │  10.0.1.0/24                │
        │       │                     │
        │       └── NAT Gateway       │
        │                             │
        │  Private Subnet             │
        │  10.0.2.0/24                │
        │       │                     │
        │    Backend / Database       │
        │                             │
        └─────────────────────────────┘
```