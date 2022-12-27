
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

**Main database storage mediums (and use case)**:

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

**Data Lakes (definition and services)**:

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

**Simple Storage Solution - S3 (definition and main features)**:

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

- 

