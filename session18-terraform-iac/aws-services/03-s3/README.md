# AWS S3 (Simple Storage Service)

What is S3? It is an incredibly popular object storage service. You don't use it like a traditional hard drive (you can't install an operating system on it); instead, you use it to store "objects" like images, videos, backups, and documents. It offers basically infinite storage capacity.

---

## S3 Structure

```mermaid
graph TD
    ACC[AWS Account] --> B1[Bucket: my-app-assets]
    ACC --> B2[Bucket: my-app-backups]
    B1 --> F1[image.png]
    B1 --> F2[video.mp4]
    B1 --> F3[folder/notes.txt]
    B2 --> F4[backup-2026.zip]

    style ACC fill:#4a90d9,color:#fff
    style B1 fill:#f0a500,color:#fff
    style B2 fill:#f0a500,color:#fff
    style F1 fill:#2ecc71,color:#fff
    style F2 fill:#2ecc71,color:#fff
    style F3 fill:#2ecc71,color:#fff
    style F4 fill:#2ecc71,color:#fff
```

---

## Storage Classes Comparison

```mermaid
graph LR
    STD[S3 Standard\nFrequent Access] --> IA[S3 Standard-IA\nInfrequent Access] --> ONE[S3 One Zone-IA\nLower cost, 1 AZ] --> GLA[S3 Glacier\nArchive, hours to retrieve]

    style STD fill:#e04b5a,color:#fff
    style IA fill:#f0a500,color:#fff
    style ONE fill:#7b68ee,color:#fff
    style GLA fill:#4a90d9,color:#fff
```

---

## Features that Make S3 Great
- **Buckets**: A bucket is just the top-level container (like a main folder) where you store your files. Bucket names have to be globally unique across all of AWS!
- **Objects**: These are the actual files you upload. Every object consists of the data itself and some metadata (like when it was uploaded).
- **Storage Classes**: Not all data is accessed frequently. S3 offers different tiers to save money.
- **Versioning**: If you turn this on, S3 keeps every version of a file you upload. If you accidentally delete or overwrite a file, you can easily restore the older version. It's a lifesaver.
- **Lifecycle Policies**: Automate your storage costs by automatically transitioning objects to cheaper storage tiers.
- **Encryption**: Ensures your data is encrypted at rest and in transit.
- **Bucket Policies**: JSON policies attached directly to the bucket to allow/deny access.

---

## Lifecycle Policy Flow

```mermaid
graph LR
    U[Upload Object] -->|Day 0| STD[S3 Standard]
    STD -->|After 30 days| IA[S3 Standard-IA]
    IA -->|After 90 days| GLA[S3 Glacier]
    GLA -->|After 365 days| DEL[Delete]

    style U fill:#2ecc71,color:#fff
    style STD fill:#e04b5a,color:#fff
    style IA fill:#f0a500,color:#fff
    style GLA fill:#4a90d9,color:#fff
    style DEL fill:#95a5a6,color:#fff
```

---

## Common Use Cases
- Storing static website assets (images, CSS, JS). You can even host an entire static website directly from S3!
- Storing application backups, database dumps, and log files.
- Acting as a massive data lake for big data analytics and machine learning.