# **AWS Power Hour: Machine Learning EP 1 Introduction to Machine Learning on AWS**

- S3 Storage Classes (in mind with optimizing costs)

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

  S3 Glacier - Instant Retreival

    - 