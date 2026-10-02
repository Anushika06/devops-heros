# S3 - Storage (Simple Storage Service)

## What is S3?
Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. You can use it to store and retrieve any amount of data from anywhere.

## Key Concepts

- **Buckets:** The fundamental container in S3 for objects. You can think of it like a top-level folder. Bucket names must be globally unique across all of AWS.
- **Objects:** The fundamental entities stored in Amazon S3. An object consists of the file data itself and its metadata (key-value pairs describing the object).
- **Storage Classes:** S3 offers different tiers based on how often you access data:
  - **S3 Standard:** Frequent access.
  - **S3 Standard-IA (Infrequent Access):** Less frequent access but requires rapid access when needed.
  - **S3 Glacier:** Low-cost storage for archiving data.
- **Versioning:** Allows you to keep multiple variants of an object in the same bucket. It helps recover from both unintended user actions and application failures.
- **Lifecycle Policies:** Rules you define to automatically transition objects between storage classes (e.g., move to Glacier after 30 days) or delete them to save costs.
- **Encryption:** Protecting your data in S3. S3 supports both server-side encryption (AWS encrypts it for you) and client-side encryption (you encrypt before uploading).
- **Bucket Policies:** JSON-based access policies attached to a bucket to grant or deny permissions across all or a subset of objects within that bucket.

## Common Use Cases
- Hosting static websites (HTML, CSS, JS files).
- Storing backups, snapshots, and archives.
- Storing user-generated media (photos, videos) for web and mobile apps.
- Data lakes for big data analytics.
