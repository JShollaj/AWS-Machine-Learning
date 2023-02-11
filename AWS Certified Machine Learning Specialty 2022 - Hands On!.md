# AWS Certified Machine Learning Specialty Course MLS C01

## Data Engineering: Moving, Storing and Processing data in AWS

### Amazon S3

#### **Overview**

- Simple Storage Service (S3)
- Store objects (files) in buckets (directories).
- Buckets must have a globally unique name.
- Max object size is 5TB.

#### **S3 For ML**

- We can create **Data Lakes** with S3 as the storage.

  - Fully managed & 11 x 9s Durability
  - Storage is decoupled from Computing resources.

- Object storage supports any file format.
  
  - Best files formats for performance are Avro & Parquet.

- We can perform data partitioning to optimize performance.

  - By Date (Hourly, Daily, Monthly).
  - By Product (ID, Family).
  - Query Patterns

#### **S3 Storage Classes**

- Amazon S3 Standard - General Purpose
- Amazon S3 Standard - Infrequent Access (IA)
- Amazon S3 One Zone - Infrequent Access
- Amazon S3 Glacier - Instant Retrieval
- Amazon S3 Glacier - Flexible Retrieval
- Amazon S3 Glacier - Deep Archive
- Amazon S3 Intelligent Tiering
