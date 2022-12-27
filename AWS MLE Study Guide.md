
# **[Official Exam Guide](https://training.resources.awscloud.com/get-certified-machine-learning-specialty/aws-certified-machine-learning-specialty-exam-guide )**

This is a summarized version of the most important topics derived from the official exam guide. Here we follow step by step each key word from the document and bring a high level description and definition for each of them. We have the following main domains to study from:  

## Domain 1: Data Engineering

Identify and compare storage mediums, classes and data sources. Know the difference between data engineering concepts such as data lakes, batch load vs streaming data.

## Domain 2: Exploratory Data Analysis

Learn how to deal with missing/corrupt data and various preprocessing techniques for NLP/CV. Learn interpretive descriptive statistics and appropriate graphing

## Domain 3: Modeling

Learn when and how to use each algorithm for specific use cases. Main focus on main terms and important concepts such as optimizers, hyperparameter tuning and model evaluation.

## Domain 4: Machine Learning Implementation

Focus on productionizing maintainable and secure ML models through AWS services. Decide when to use out of the box ML models instead of building your own. Learn MLOPs architectures.

(*Tip: Use CTRL+F to navigate to specific term of interest*)

------

## **Domain 1: Data Engineering**

### **Main database storage mediums (and use case)**

- Aurora, RDS, Redshift (Relational) &rarr; For ERP/CRM

- DynamoDB (NoSQL-Key Value) &rarr; E-Commerce / Gaming / High Traffic

- ElastiCache, MemoryDB (In-Memory) &rarr; Cashing / Geo-Spatial

- DocumentDB (Document) &rarr; Content Management / User Profiles

- KeySpaces (Wide Column) &rarr; Equipments / Fleet / Routes

- Neptune (Fraud/Graph) &rarr; Recommenders / Social Networks

- LedgerDB (Ledger) &rarr; Banking / Supply Chain

(Check the [table here](https://aws.amazon.com/products/databases/) for a more comprehensive overview)

(Review [2022 ReInvent](https://www.youtube.com/playlist?list=PL2yQDdvlhXf_22xqaqPb13gDRDOq2Sjg4) for appropriate use of storage solutions)

</br>

### **Data Lakes (definition and services)**

![Data Lakes in AWS](https://d1.awsstatic.com/Data%20Lake/320x320-what-is-a-data-lake.b32634fa96e91bb5670b885be9428a2c0c40c76d.png) 

Definition: Centralized repository that allows you to store all your structured and unstructured data at any scale.

In a data lake we can perform big data processing and real time analytics for machine learning use cases.

In AWS we use the following services to create a data lake:  

- S3 (Storage) &rarr; (Standard, IT, IA, One-Zone IA, Glacier, Archive).

- Athena (Analytics) &rarr; Use Python/SQL to query data.

- EMR (Elastic MapReduce) &rarr; Big Data Pipelines for streaming and analytics.

- Lake Formation (Governance) &rarr; CRUD lakes with SQL for security and governance.

- Glue (ETL) &rarr; Event driven data integration tool.

(Review the [following chart here](https://aws.amazon.com/big-data/datalakes-and-analytics/) for more insights on analytics)

</br>

### **Simple Storage Solution - S3 (definition and main features)**

Storage solution used for:  

- Data Lakes
- Back-Ups
- Apps
- Archive

It has the following features:  

- Unique Access Points &rarr; for large, shared datasets (with different restriction policies).

- Batch Operations &rarr; for modifying object metadata, copy objects, IAM policy management and Lambda functions.

- Block Public Access &rarr; based on bucket or account level.

- Multi-Region Access points &rarr; route requests based on proximity.

- Object Lambda &rarr; invoking lambda functions to transform objects.

- Object Lock &rarr; Prevent object from being overwritten, deleted (WORM - write once, read many).

- Replication &rarr; Of objects in buckets (fully managed and elastic).

- Analytics &rarr; Using Storage Lens for insights across S3 Objects.

</br>

### **S3 Storage Classes**

S3 is composed of different tiers, based on the required use case, as follows:

1. Standard &rarr; For big data analytics, game applications, dynamic sites etc.

2. Intelligent-Tiering &rarr; Automatically moves to most effective tier.

3. Infrequent-Access &rarr; Less frequent, but rapid access (think backups).

4. Infrequent-Access One Zone &rarr; Single AZ, costs 30% less than IA (less accessed backups).

5. Glacier (Instant Retrieval) &rarr; For rare access, but retrieval in ms. (online file-sharing, disaster recovery).

6. Glacier (Flexible Retrieval) &rarr; For rare access, retrieval 1-5 min (digital media, legacy docs).

7. Glacier (Deep Archive) &rarr; Rare Access, retrieval within 48 hours (legacy docs, low importance - think auditing).

8. Outposts &rarr; pool of AWS compute and storage capacity deployed at a customer site (online multiplayer gaming).

</br>

### **EFS - Elastic File System**

File storage solution which:

- Enables sharing data without provisioning & can scale automatically.

- Supports up thousands of EC2 instances connecting to a file system concurrently.

- Can store petabytes (2^50 bytes).

- Option for EFS Infrequent-Access One Zone &rarr; Price performance optimized on accessed data (saves up to 92% of file storage).

</br>

### **EBS - Elastic Block Store**

Block storage solution which:

- Think of hard drive for single EC2.

- Block storage (equally sized blocks).

- Performance advantage (EBS Encryption with low latency).

- Use case for long-term logs & distribution of mass content.

- Have snapshots of backups for compliance.

- Has automated lifecycle manager based on given policies.

</br>

**Summary**: We have many options which overlap and are context dependent. For longest term storage follow this pattern:

S3 &rarr; EBS &rarr; EFS (Different tiers based on given context).

For higher performance on very small object size we use the listed DBs for each scenario. 

The main focus should be on the use case, tier and pricing optimization.

</br>

### **Batch Load vs Streaming**

The main difference is that:

- Batch load requires processing data over all (or most data) in a dataset with large batches of data. Latency is usually in minutes or hours. (Use BATCH or Glue). AWS Glue is an event driven ETL tool which has many features such as no code, monitoring data quality, data prep etc.

- Streaming processes in real time in micro-batches in seconds or milliseconds for simple functions (Kinesis or MSK).

**For streaming we have the following services:**

- Kinesis Video Streams &rarr; Streaming media from connected devices to AWS for storage/ML/Analytics. Fully managed ingestion, storage and processing. Good integration with MXNet, TensorFlow, OpenCV. Best use cases: Smart Home/City & Industrial Automation.

- Kinesis Data Streams &rarr; Real time read & process data streams. Use cases: Log Intake, Real Time Metrics/Analytics, Power Events.

- Kinesis Data Firehose &rarr; Real time analytics (BI & Dashboards). Can also batch, compress, encrypt & scale.

- Kinesis Data Analytics &rarr; For real time metrics, analytics and interactive data streams.

- Managed Service Kafka (MSK) &rarr; Managed Kafka solution if you have existing Kafka solution integrated for the data stream.

**Summary**: For Batch operations we have GLUE or massive BATCH operations which we can schedule. We can also deploy open source solutions (f.ex Airflow). For streaming we can use firehose mainly for loading streaming data transfer while data streams for real time ingestion.

*Refer [here](https://www.whizlabs.com/blog/aws-kinesis-data-streams-vs-aws-kinesis-data-firehose/) for more details.*

</br>

### **EMR (Elastic MapReduce)**

Big data analytics platform hosted in AWS used for petabyte scale analytics. EMR has the following features:

- Half-cost (-50%) less cost than on premises solutions.

- 1.7x times faster than Apache Spark.

- Instant scaling and fully managed resources.

- Used mainly for big data ML, Clickstream analysis, ETL, etc.


*To learn more about Apache Spark try [this course](https://www.coursera.org/learn/scala-spark-big-data)*

</br>

------

</br>

## **Domain 2: Exploratory Data Analysis**

### **How to deal with missing data**

To deal with missing data we can impute, delete rows/columns or not do anything.

### **Data Imputation Methods (Numeric)**

- KNN Imputer (Using mean value from n-neighbors). **Best One**

- MICE (Using predictive mean matching through chain equation).

- Bayesian PCA (Maximizing marginal likehood through BPCA).

- Bayesian Linear Regression (Mean imputation as a linear combination of features).

- Others (Mean, Mode, Median, Forward/Backward, Interpolation).

### **Data Imputation Methods (Non-Numeric)**

- Most frequent value.

-Add 'Unknown' or NA.

- Category specific imputation (f.ex animal for dogs & cats).

### **How to deal with corrupt data**

- Delete row/columns.

- Create new category.

- Imputation (See Above).

- Predictive model for missing values.

### **Types of missing/corrupt data**



