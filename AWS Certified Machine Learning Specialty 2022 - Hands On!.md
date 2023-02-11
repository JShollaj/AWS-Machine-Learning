# AWS Certified Machine Learning Specialty Course MLS C01

## Data Engineering: Moving, Storing and Processing data in AWS

### Amazon S3

#### **Overview**

- Simple Storage Service (S3)
- Store objects (files) in buckets (directories).
- Buckets must have a globally unique name.
- Max object size is 5TB.

- Durability and Availability:

  - Durability of: **11 x 9s** &rarr; If we have 10 million objects, lose 1 every 10,000 years.

  - Availability of: **4 x 9s** &rarr; Not available ~53 minutes in a year.

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

- Amazon S3 **Standard - General Purpose**

  - Used for frequently accessed data
  - Sustain 2 concurrent facility failures.
  - Low latency & High throughput.
  - Used for Big Data Analytics, Mobile & Gaming etc.

- Amazon S3 **Standard - Infrequent Access (IA)**

  - Less frequent, but required rapid access.
  - Lower cost than S3.
  - Lower Availability (99.9%).
  - Used for Disaster Recovery, Backups etc.

- Amazon S3 One Zone - Infrequent Access

  - High durability (11x9s), but only in single AZ.
  - Lower cost than S3 Standard IA.
  - Storing secondary data.

- Amazon S3 Glacier - Instant Retrieval

  - Lowest cost (meant for deep archives).
  - Millisecond retrieval, objects but needs to be stored for at least 90 days.

- Amazon S3 Glacier - Flexible Retrieval

  - Minimum storage duration (90 days).
  - Different types of retrievals:
    - Expedited (1-5 minutes)
    - Standard (3-5 hours)
    - Bulk (5-12 hours) - Free tier

- Amazon S3 Glacier - Deep Archive

  - Cheapest ($1 per TB)
  - Longest term storage.
  - Minimum storage duration (180 days).
  - 

- Amazon S3 Intelligent Tiering
