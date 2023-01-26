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

    - Cheaper, simpler method for periodically ingesting data.

    - Services which can enable it

  - Identify and implement a data-transformation solution.


