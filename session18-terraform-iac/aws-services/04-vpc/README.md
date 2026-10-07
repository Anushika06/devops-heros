# AWS VPC (Virtual Private Cloud)

What is VPC? A VPC is your own private slice of the AWS cloud. It's a virtual network that closely resembles a traditional network you'd operate in your own data center, but it's completely software-defined. Everything you launch (like EC2 instances or RDS databases) lives inside a VPC.

---

## VPC Architecture

```mermaid
graph TD
    IGW[Internet Gateway] <-->|public traffic| VPC

    subgraph VPC["VPC  10.0.0.0/16"]
        subgraph AZ1["Availability Zone 1"]
            PUB1[Public Subnet\n10.0.1.0/24]
            PRIV1[Private Subnet\n10.0.2.0/24]
        end
        subgraph AZ2["Availability Zone 2"]
            PUB2[Public Subnet\n10.0.3.0/24]
            PRIV2[Private Subnet\n10.0.4.0/24]
        end
        NAT[NAT Gateway]
    end

    PUB1 --> NAT
    NAT -->|outbound only| IGW
    PRIV1 -->|internet updates| NAT
    PRIV2 -->|internet updates| NAT

    style IGW fill:#1abc9c,color:#fff
    style PUB1 fill:#2ecc71,color:#fff
    style PUB2 fill:#2ecc71,color:#fff
    style PRIV1 fill:#e04b5a,color:#fff
    style PRIV2 fill:#e04b5a,color:#fff
    style NAT fill:#f0a500,color:#fff
```

---

## Networking Basics
- **CIDR (Classless Inter-Domain Routing)**: A way to define a block of IP addresses for your network (like `10.0.0.0/16`, giving you 65,000+ IPs).
- **Subnets**: You chop your VPC's CIDR block into smaller chunks. Each subnet lives in one specific Availability Zone.
- **Public vs Private Subnet**: A subnet is "public" if it has a direct route to the internet. You usually put load balancers in public subnets and databases in private subnets.

---

## Security Groups vs NACLs

```mermaid
graph LR
    Internet -->|traffic| NACL[Network ACL\nSubnet Level\nStateless]
    NACL --> SG[Security Group\nInstance Level\nStateful]
    SG --> EC2[EC2 Instance]

    style Internet fill:#95a5a6,color:#fff
    style NACL fill:#f0a500,color:#fff
    style SG fill:#e04b5a,color:#fff
    style EC2 fill:#4a90d9,color:#fff
```

---

## How Traffic Moves
- **Internet Gateway (IGW)**: The door to the internet for your VPC.
- **Route Tables**: Act like a GPS for your network traffic, dictating where traffic is directed.
- **NAT Gateway**: Allows private subnet resources to reach the internet for outbound traffic (like updates), while blocking inbound connections from the internet.

## Security
- **Security Groups**: Stateful firewall at the **instance** level. Allow a request in, and the response is automatically allowed out.
- **Network ACLs (NACLs)**: Stateless firewall at the **subnet** level. You must explicitly allow traffic both in and out.