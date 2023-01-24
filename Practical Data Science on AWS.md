# Analyze Datasets and Train ML Models using AutoML

## Introduction to **Practical Data Science**

</br>

- Focus on massive data which cannot be run locally. (Elastic pay-as-you go infrastructure).

- Ingest and analyze data:

  - Data Exploration & Bias Detection:

    - Amazon S3 & Amazon Athena.

      - Athena &rarr; serverless running SQL queries (petabytes). No data movement required.

    - Amazon Glue.

      - Glue Catalog &rarr; creates reference s3 to data mapping. (Metadata about schema etc.)

      - Glue Crawler &rarr; automatically infers data schema and updates data catalog.

    - Sagemaker (Data Wrangler, Clarify).

      - Data Wrangler &rarr; can ingest data from data lakes, warehouses, databases.

- Prepare & transform:

  - Feature Engineering and Feature Store:

    - Sagemaker Data Wrangler.

    - Sagemaker Feature Store.

    - Sagemaker Processing Jobs.

- Train & Tune:

  - Automated ML & Model Train/Tune

    - Sagemaker Autopilot.

    - Sagemaker Training & Debugger.

    - Sagemaker Hyperparameter Tuning.

- Deployment & Production:

  - Model Deployment & Automated Pipelines

    - Sagemaker Endpoints

    - Sagemaker Batch Transform

    - Sagemaker Pipelines

- Typical ML workflow and tools:

![Alt text](ML%20Workflow.png)

- Statistical bias and feature importance:

  - Statistical Bias: Tendency to overestimate/underestimate a parameter.

  - Biased datasets &rarr; biased models. F.ex vastly more product reviews for A then B.

  - Different Types of Biases:

    - Activity Bias (f.ex popularity of product B than A).

    - Social Bias (f.ex preconceived notions about background).

    - Selection Bias (f.ex streaming movie recommendation wolves vs favorite actors).

  - Data Drifts types (data distribution significantly varies from ):

    - Covariant Drift &rarr; distribution of features changes.

    - Prior probability drift &rarr; 