# **AWS Power Hour: Machine Learning EP 1 Introduction to Machine Learning on AWS**

- **S3 Storage Classes** (in mind with optimizing costs)

  - S3 Standard

    - Store frequently accessed data. Readibly accessible

    - Durability 99.(11x9)% - chance that data will be stored.

    - Avalaibility 99.(4x9)% - chance that data will be available.

  - S3 IA Standard

    - Less frequently accessed data. (less than once/month)

  - S3 One Zone IA

    - Data which we dont need equally available at all times.

    - Instead of replicating data across 3 Availability Zones, replicate in only one.

    - For example, previous versions of data lake instead

  - S3 Glacier - Instant Retreival

    - Archival type of data. F.ex variety of logs, ETL jobs.

  - S3 Intelligent Tiering

    - ML Based storage. Shifts datasets across different storage types depending on access patterns it observes.

</br>

- **Moving Data: Kinesis Services**

  - Kinesis Video Streams:

    - Secure stream video from connected services.

  - Kinesis Data Streams:

    - High throughput data streams integration.

  - Kinesis Firehose:

    - Can be configured, to automatically stream data into the data lake.

  - Kinesis Data Analytics:

    - Doing real time analytics.

- Amazon Kinesis Data Streams producer.

  - **Producer** is an application that puts user data records into a Kinesis data stream (also called data ingestion).

    - Performance Benefits.

    - Consumer-Side Ease of Use.

    - Asynchronous Architecture.

    - Producer Monitoring.

- Connecting to Zeppeling Notebook

  - Setting up a schema, and execute queries.

- Delivering streams (Firehose):

  - Transforming source records with Lambda

- AWS Glue

  - ETL Tool.

  - Spark Analytics Kernel Image Integration with ETL Glue. (Can use PySpark) (Configure Spark Session).

---

## **AWS Power Hour: EDA on AWS**

- Sagemaker Data Wrangler:

  - Tool from within studio.

  - Map various data stores (f.ex redshift, lake formation). Can also write queries before pulling in data).

  - Generate insights to better understand data that we have. (Data quality checks).

- Can do the following:

- Balancing Data:

  - Random Oversampling

  - Random Undersampling

  - SMOTE (Synthetic Minority Oversampling TEchnique)

- Encoding (Mainly for Categorical):

  - One-hot/dummy encoding

  - Label / Ordinal encoding

  - Target encoding

  - Frequency / count encoding

  - Binary encoding

  - Feature Hashing

  - Nominal variables &rarr; NO order

  - Ordinal variables &rarr; HAVE order

- Process Numeric:

  - Standard Scaler (subtracting mean from each value and scaling to unit variance).

  - Robust Scaler (scaling in a way robust to outliers).

  - MinMax Scaler (scaling each feature to a given range).

  - Max Absolute Scaler (maximal absolute value of each feature in the training set will be 1.0)

- Data Flow &rarr; similar to Alteryx or Knime

- Sagemaker Autopilot helps automating end to end projects.

  - Feature Store: Can be stored and shared interoperatibly. Linear tracking for each feature.

  - Spark connector enabling to ingest data in bulk.

  - 