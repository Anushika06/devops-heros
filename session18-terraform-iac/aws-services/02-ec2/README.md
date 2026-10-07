# AWS EC2 (Elastic Compute Cloud)

What is EC2? In simple terms, EC2 allows you to rent virtual computers (servers) in the cloud. Instead of buying physical hardware, plugging it into a rack, and installing an operating system, you can spin up a server in AWS in seconds, and tear it down when you're done.

---

## EC2 Instance Architecture

```mermaid
graph TD
    AMI[AMI - Blueprint] -->|used to launch| EC2[EC2 Instance]
    KP[Key Pair] -->|secure SSH access| EC2
    SG[Security Group] -->|firewall rules| EC2
    EBS[EBS Volume] -->|attached storage| EC2
    EC2 -->|has| PUB[Public IP]
    EC2 -->|has| PRIV[Private IP]

    style AMI fill:#7b68ee,color:#fff
    style EC2 fill:#4a90d9,color:#fff
    style KP fill:#f0a500,color:#fff
    style SG fill:#e04b5a,color:#fff
    style EBS fill:#2ecc71,color:#fff
    style PUB fill:#1abc9c,color:#fff
    style PRIV fill:#95a5a6,color:#fff
```

---

## Key Concepts
- **AMI (Amazon Machine Image)**: Think of an AMI as a blueprint or template for your server. It contains the operating system (like Ubuntu, Windows, or Amazon Linux) and any pre-installed software you want. You use an AMI to launch an instance.
- **Instance Types**: Servers come in different shapes and sizes. Some have lots of CPU for heavy processing, others have massive amounts of RAM for in-memory databases. You pick the instance type that matches your workload.
- **Key Pairs**: To securely log into your instance (especially Linux servers via SSH), AWS uses public key cryptography. You keep the private key on your laptop, and AWS puts the public key on the server.
- **Security Groups**: This is essentially a virtual firewall attached directly to your EC2 instance. You configure rules to say things like "Only allow web traffic on port 80" or "Only allow SSH from my specific IP address".
- **EBS (Elastic Block Store)**: If EC2 is the brain and CPU, EBS is the hard drive. It's network-attached storage that you attach to your EC2 instance to store your files and databases.

---

## Instance Lifecycle

```mermaid
stateDiagram-v2
    [*] --> Pending : Launch
    Pending --> Running : Ready
    Running --> Stopping : Stop
    Stopping --> Stopped : Stopped
    Stopped --> Pending : Start
    Running --> ShuttingDown : Terminate
    Stopped --> ShuttingDown : Terminate
    ShuttingDown --> Terminated : Done
    Terminated --> [*]
```

---

## IP Addresses
- **Public IP**: An address that can be reached from anywhere on the internet.
- **Private IP**: An address that is only reachable from inside your AWS network (VPC).

## Common Use Cases
- Hosting web servers or applications.
- Running background processing jobs or batch scripts.
- Hosting databases (though RDS is often better for this if you want it managed).