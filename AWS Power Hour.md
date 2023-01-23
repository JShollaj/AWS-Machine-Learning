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

    - 