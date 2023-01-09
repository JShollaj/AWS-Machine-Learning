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

  ![Unsupervised](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673240400/F9f6-J_gx5vlxiB2SDDP4w/tincan/b96a0de6b327457590ce8bf1be4022c35b8f5a55/assets/5qKovKTmhBGq_35e_sJVSOFncmvuWWFhH.png)

  - **Reinforcement learning** &rarr; training model learns from its environment by being rewarded for correct moves and punished for incorrect moves. F.ex *autonomous driving*.

  ![Reinforcement](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673240400/F9f6-J_gx5vlxiB2SDDP4w/tincan/b96a0de6b327457590ce8bf1be4022c35b8f5a55/assets/vrGPGbsOPnvY-7Sk_yermJAn8zmHHz8Z6.png)

</br>

### **What are some potential problems with machine learning?**

- Basically a combination of:

  - Poor Data / Lack of data.

  - Unexplainability (Too complex). Or too simplistic (low accuracy).

  - Take uncertainty (black swan events into account).

</br>

### **Planning a Machine Learning Project**

- Is a machine learning solution appropriate for my problem?

  - Requires 4 main components:

    - **Complex logic** (f.ex recommender).

    - **Requires scalability** (f.ex personalized recommendations to million users).

    - **Requires personalization** (tailored specific to user).

    - **Requires responsiveness** (response in milliseconds to personalization).

  - We dont need to use ML if:

    - Can be solved with traditional algorithms.

    - Does not require adapting to new data.

    - Requires 100% accuracy.

    - Requires full interpretability.

- Is my data ready for machine learning?

  - Types of data:

    - Document

    - Audio

    - Images

    - Video

- Checklist requirement for using data:

  - **Availability** (not requiring significant preprocessing). &check;

  - **Accessibility** (on demand with CRUD capabilities). &check;

  - **Respect Privacy** (f.ex ethnicity, salary). &check;

  - **Security** (f.ex respect regulations). &check;

  - **Relevant** to the scope an project. &check;

  - **Fresh** and recent data. &check;

  - **Representative** and encompassing features. &check;

  - **Unbiased** without agenda. &check;

</br>

### **How will machine learning impact a project timeline?**

- Machine learning project expectations (weeks up to months). Keep track of model drift (changes in data distribution)!

![Lifecycle](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673244000/BDtSbQM-16gMctMnquPoiQ/tincan/bfb191eed840c42f824d44e8698b1bac29383d8b/assets/ToDGeO4MF-OKVaEm_LWVgwfitLKRtwY05.png)

- A typical timeline for ML projects (rough benchmark).

![timeline](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1673244000/BDtSbQM-16gMctMnquPoiQ/tincan/bfb191eed840c42f824d44e8698b1bac29383d8b/assets/5ASJnvv4cGifR5ml_PZifQ5iNwSxaakX8.png)

</br>

### **What early questions should I ask in deployment?**

- What is the likely computational cost of generating predictions with your model?

- How quickly does your data change?

- How significant are the changes needed to deploy?

- Does the model’s performance meet the business need?

</br>

### **Building a Machine Learning Ready Organization**

- How can I prepare my organization for using ML?

  - Have a robust ML strategy.

  - Data strategy.

  - Culture of learning and collaboration.

  - Find the right problem (data, complexity, ).

  - Fail forward (deliberate failure - keep experimenting).

  - Scale beyond proofs of concept (POC).

  </br>

### **Machine Learning for Business Challenges**

- Key Takeaways:

  - Defining **scope** of ML problem:

    - Specific business problem we are trying to solve.

    - Current state.

    - What are / what is causing pain points.

    - Impact of the problem.

    - How do we define success.

  - **Input** gathering:

    - Do we have sufficient data?

    - Is there labeled data?

    - How difficult to obtain labeled data?

    - What are the main features?

    - Where is data located?

    - Data quality check?

  - **Output** definitions:

    - What business metrics define success?

    - Trade-offs?

    - Existing baselines (if not, simplest solution)?

    - How important is runtime and performance?

- Image **Classification** Problem:

  - We need training data, and groundtruth label.

  - Feature engineering: deciding set of measurements for each instance.

  - Choose classifier model (select the one with higher accuracy on *validation* set and ***good business values***):

    - **SVM** (creates a line which separates the data into classes).

    - **Naive Bayes** (uses Bayes rule together with a strong assumption that the attributes are conditionally independent).

    - **Logistic Regression** (predicts the probability of a binary (yes/no) event).

    - **Deep Neural Networks**

</br>

- **Reinforcement** Problem: Training a Robot

  - Reward / Punish agent based on choice and reiterate.

  - No presentation of input or output pairs.

  - Agent needs to gather useful experiences.

  - Evaluation is often concurrent with learning.

  </br>

- **Automating Speech Tasks** Problem: Pollexy

  - Speech to task and automation.

  </br>

### **Machine Learning Terminology and Process**

- **Step 1: Business Problem**

  - What are we trying to solve (see scope,input and output above).

  </br>

- **Step 2: Machine Learning Problem**

  - What model could solve most of our issues.

  - Key Elements:

    - Attributes from dataset &rarr; **Observations**

    - Future Outputs &rarr; **Labels**

    - Used attributes to predict labels &rarr; **features**

  - Framing ML problem:

  - ![sklearnguide](https://scikit-learn.org/stable/_static/ml_map.png)

- **Step 3: Develop Datasets**

  - Data collection and integration

  - 3 different types:

    - **Structured** (Organized in tabular/databases)

    - **Semi-Structured** (semi - csv, json)

    - **Unstructured** (video, image etc.)

- **Step 4: Data Preparation**

  - Data Cleaning:

    - Could introduce new variable

    - Remove

    - Or Imputation (best guess)

  - Imputation:

    - You can refer here for a comprehensive review of the [**best imputation methods**](https://www.kaggle.com/discussions/general/375794).

    </br>

  - Data Shuffling:

    - We dont want to make predictions just based on order (could lead to bias) - so we shuffle.

  - Test/Val/Train Split:

    - Predict new examples (by holding from our dataset).

    - Train ~ 70% of data.

    - Test ~ 20% of data.

    - Validation ~ 10% of data.

    </br>

  - Cross Validation Techniques:

    - Leave-One-Out (Only use one data point as our test sample, run training with other examples) - Expensive

    - K-Fold (For each fold we train the model and keep track of error).

    </br>

- **Step 5: Data Visualization and Analysis**

  - **Feature** = Attribute in training dataset.

  - **Label** = NOT in training; what we are trying to predict.

  - Types of Visualization for EDA:

    - Statistics

    - Scatterplots

    - Histograms

  - Features and Target Summary:

    - 



 






















