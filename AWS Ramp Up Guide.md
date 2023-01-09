# **[Machine Learning Ramp Up Guide](https://training.resources.awscloud.com/get-certified-machine-learning-specialty/aws-ramp-up-guide-machine-learning-2)**

## **Step 1: Learn AWS Machine Learning (ML) fundamentals**

### a) Machine Learning Essentials for Business and Technical Decision Makers

### **Introduction to Machine Learning: Art of the Possible**

</br>

  - ML &rarr; using math to find patterns in data & update model and training data to improve accuracy.

   ![Process](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673240400/F9f6-J_gx5vlxiB2SDDP4w/tincan/b96a0de6b327457590ce8bf1be4022c35b8f5a55/assets/UNFm4yYCD78mPMrq_L7sIBPrfXqGsHIYe.png)

  - Key Terms (M.T.T.D):
  
    **Model** &rarr; The output of an ML algorithm trained on a data set; used for data prediction.

    **Training** &rarr; The act of creating a model from past data.

    **Testing** &rarr; Measuring the performance of a model on test data.

    **Deploying** &rarr; Integrating a model into a production pipeline.

    </br>

  - History of Amazon and ML:

![History](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673240400/F9f6-J_gx5vlxiB2SDDP4w/tincan/b96a0de6b327457590ce8bf1be4022c35b8f5a55/assets/zcmzaPPidRjKWA2E_UKq5ypWPEFm4XE0D.png)

**Amazon Flywheel** - How investing in specific key business operations can reinforce other processes and create a positive feedback loop.

![Amazon Flywheel](Amazon%20Flywheel.png)

**AWS ML Flywheel** - Uses data collected from parts of a business operation, a model to predict future outcomes, and provides ways to continuously improve efficiency.

![ML Flywheel](AWS%20ML%20Flywheel.png)

**Amazon uses ML in the following ways:**

- Product recommendations and promotions.

- Alexa and voice interactions through NLP.

- Ship 1.6M packages per day.

**Amazon AI/ML Services:**

- Amazon Forecast: Time series forecasting (just upload data within requirements).

- Amazon Fraud Detector: Fully managed service that spots online payment fraud and creation of fake accounts.

- Amazon Personalize: Recommender where you select a training algorithm to use on the data, solution model training, and solution deployment.

- Amazon Polly: Text to speech.

- Amazon Transcribe: Speech to text (Polly's opposite).

- Amazon SageMaker: Think of Jupyter lab on steroids.

</br>

### **How does machine learning work?**

- **AI**: Automate and accelerate tasks performable by humans through natural intelligence. Two types:

  - **Narrow** &rarr; AI imitates human intelligence in a single context.

  - **General** &rarr; AI learns and behaves with intelligence across multiple contexts.

- **ML vs AI: Difference**: AI ingests data and imitates human knowledge vs ML improves model on training data (subset)

![Difference](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673240400/F9f6-J_gx5vlxiB2SDDP4w/tincan/b96a0de6b327457590ce8bf1be4022c35b8f5a55/assets/Omo6IawSrRpBSmQh_EMmcqjVa-JuFe0QF.png)

- **ML vs Traditional Programming**: ML is teaching a computer to recognize patterns by example, rather than programming it with specific rules.

![MLvsProgramming](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673240400/F9f6-J_gx5vlxiB2SDDP4w/tincan/b96a0de6b327457590ce8bf1be4022c35b8f5a55/assets/hxfNyqDM1_O1MweC_eyA4WWgM4-rp-qF4.jpg)

- **3 Main ML Categories:**

  - **Supervised learning** &rarr; model learns from a data set containing input values and paired output values that you would like to predict. Could be *classification* (spam detection) or *regression* (forecasting demand).

  ![Supervised](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673240400/F9f6-J_gx5vlxiB2SDDP4w/tincan/b96a0de6b327457590ce8bf1be4022c35b8f5a55/assets/lQNL_83C-ppyf0qE_rlLY75xnMf-J8a1x.png)

  - **Unsupervised learning** &rarr; training model learns from data without any guidance. The objective is pattern and structure recognition. Could be *clustering* (customer segmentation) or *association* (finding regularities among products).

