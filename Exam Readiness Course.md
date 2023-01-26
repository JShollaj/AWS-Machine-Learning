# Exam Readiness for MLE

A brief refresher into what will be tested. We have covered below a concise version of will be included and we need to know in depth:

---

## 1. Course Introduction

</br>

- Understand basic algorithms & hyper-parameter tuning.

- Understanding ML Pipeline.

- Experience with ML and Deep Learning frameworks.

- Understanding of and experience in model training, deployment & operational best practices.

- Use this guide as a starting point (or before exam) - to identify weaknesses and dig deeper.

</br>

## 2. Exam Overview and Test-Taking Strategies

</br>

- Focus on key phrases, and qualifier to easily discard distracting questions.

- Focus on AWS Services, and see if there is a correlation between the assumption and the service.

- Prepare for some minor calculations at hand.

- Read and understand the question before reading answer options (pretend the answer options aren't even there at first).

- Identify the key phrases and qualifiers in the question.

- Try to answer the question before even looking at the answer choices, then see if any of those answer choices match your original answer.

- Eliminate answer options based on what you know about the question, including the key phrases and qualifiers you highlighted earlier.

- If you still don't know the answer, consider flagging the question and moving on to easier questions. But remember to answer all questions before the time is up on the exam, as there are no penalties for guessing.

</br>

## 3. Domains Which Will Be Covered

</br>

### **Data Engineering**

</br>

- **Create data repositories for Machine Learning**.

  - Think of Data Lake as an all encompassing solution for ML tasks.

  - *Lake Formation* as a single place to manage access controls for data in your data lake

  - Recall storage solutions and use cases.

  - ![S3](images/S3.png)

  - *Amazon FSx* for Lustre &rarr; for running training jobs several times using different algorithms and parameter (when data is already on S3).

  - If data is already in EFS &rarr; use that as training data source (faster training start times).

  - Images per second that each file system can load (Amazon FSx fastest &rarr; S3 slowest).

  - Topics to study in depth:

    - AWS Lake Formation &#x2610;

    - Amazon S3 (as storage for a data lake) &#x2610;

    - Amazon FSx for Lustre &#x2610;

    - Amazon EFS &#x2610;

    - Amazon EBS volumes &#x2610;

    - Amazon S3 lifecycle configuration &#x2610;

</br>

- **Identify and implement a data-ingestion solution**.

  - Batch vs Streaming Ingestion

  - Batch has the following attributes:

    - Cheaper, simpler method for periodically ingesting data.

    - Services which can enable batch ingestion:

      - AWS Glue (ETL Service).

      - AWS Database Migration Service (Reads  historical data from source systems, such as RDS, Warehouses, and NoSQL databases, at any desired interval).

      - AWS Step Functions (to automate the abovementioned).

  - Streaming has the following attributes:

    - Data is sourced, manipulated, and loaded as soon as it is created or recognized.

    - More expensive, harder to maintain.

    - The following services are associated with streaming data:

      - Kinesis Video Stream

      - Kinesis Data Analytics

      - Kinesis Firehose

      - Kinesis Data Stream

    - Topics to study more in depth:

      - Amazon Kinesis Data Streams &#x2610;

      - Amazon Kinesis Data Firehose &#x2610;

      - Amazon Kinesis Data Analytics &#x2610;

      - Amazon Kinesis Video Streams &#x2610;

      - AWS Glue &#x2610;

      - Apache Kafka &#x2610;

  - Identify and implement a data-transformation solution.

  </br>

  ---

  </br>

### **Domain 2: Exploratory Data Analysis**

</br>

- Sanitize and prepare data for modeling.

  - Multivariate statistics (correlation & relationships).

  - Attribute statistics (f.ex mean, SD).

  - Individual statistics (f.ex rows, columns).

  - Clean data

    - Same scale (f.ex miles vs km).

    - Columns dont have multiple features (f.ex date, text).

    - Clear Outliers.

    - Imputation & dealing with missing data.

  - Topics to study more:

    - Dataset generation

      - Amazon SageMaker Ground Truth

      - Amazon Mechanical Turk

      - Amazon Kinesis Data Analytics

      - Amazon Kinesis Video Streams

    - Data augmentation

    - Descriptive statistics

    - Informative statistics

    - Handling missing values and outliers

- **Perform feature engineering.**

  - Reduce features (PCA, t-distributed stochastic neighbor embedding).

  - For numerical we can transform (multiply, square, cube).

  - Categorical Feature Engineering:

    - Ordinal &rarr; ORDER MATTERS.

    - Nominal &rarr; ORDER DOESN'T MATTER.

  - Common techniques for scaling (clues in names):

    - Mean/variance standardization.

    - MinMax scaling.

    - Maxabs scaling.

    - Robust scaling.

    - Normalizer.

  - Topics to study:

    - Scaling.

    - Normalizing.

    - Dimensionality Reduction.

    - Date Formatting.

    - One-Hot Encoding.

</br>

