
# **[Machine Learning Engineering Guide](https://training.resources.awscloud.com/get-certified-machine-learning-specialty/aws-certified-machine-learning-specialty-exam-guide )**

This is a summarized version of the most important topics derived from the official guide. Here we follow step by step each key word from the document and bring a high level description and definition for each of them. We have the following main domains to study from:  

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

- Add 'Unknown' or NA.

- Category specific imputation (f.ex animal for dogs & cats).

### **How to deal with corrupt data**

- Delete row/columns.

- Create new category.

- Imputation (See Above).

- Predictive model for missing values.

### **Types of missing/corrupt data**

- M.C.A.R &rarr; Missing completely at random (No Pattern).

- M.A.R &rarr; Missing completely at random (Usually machine error which can be inferred).

- M.N.A.R &rarr; Missing not at random (Deliberately hiding info like salary).

- S.M.D &rarr; Structurally missing data (We know pattern and can infer).

### **Types of preprocessing**

- NLP (lowercase, punctuation, numbers, special char, emojis etc.).

- CV (greyscale, standardize image, augment data etc.).

- Most use cases are context and case dependent on what the scope or objective is.

### **Formatting data**

- Choose the right data format (parquet is usually faster).

- Put similar items under same columns.

- Avoid blank rows.

- Avoid trailing whitespaces.

- Keep format consistent (f.ex address, currency, date etc.).

- Quality > Quantity of data.

</br>

### **Normalizing data**

- Decimal place (f.ex in excel accounting nr.).

- Data type normalization (f.ex in excel general to currency).

- Z Score normalization (Normalize relative to Standard Deviation). (Value - Mean) / SD

- Linear normalization (Base on Max-Min). (X - min(x))/Max(X) - Min(X).

- Clipping normalization (Re-assign Outliers)

- Normalized Standard Deviation (SD/Mean)

</br>

### **Normalization vs Standardization**

- Normalization - End result on all dataset after performing standardization.

- Standardization - Individual row based transformation.

### **Data Augmentation Techniques**

Chiefly for text & image based data. For numerical we can use synthetic simulated data.

**For text data:**

- Synonym replacement (ELmo, BERT).

- Lexical based replacement (NLTK, Spacy).

- Random Insertion/Deletion/Swapping.

- Backtranslation (F.ex ENG->FR->ENG).

- Generative Models (Text Attack, NLPAug, TextAugment).

**For image data:**

- Data warping (preserves label, geometric/color transformation).

- Oversampling (GAN, Feature Space, Mixing Images).

- Combination of both.

</br>

### **Labeled data:**

- Manual through domain knowledge (customizable against bias).

- Mechanical turk (access to workforce in marketplace).

- Sagemaker Groundtruth Plus (Share data and required labeling & and you get them labeled).

</br>

### **Feature Engineering Concepts:**

- Binning (Group breakdown).

- Tokenization (Word / Character breakdown).

- Adding synthetic features.

- One hot Encoding (for categorical).

- PCA.

</br>

### **Graphing Data:**

Use the [following guide](https://www.sqlbi.com/ref/power-bi-visuals-reference/) for which chart to use for each scenario. A summarized version is as below:

- Comparison (Clustered Bar Chart).

- Change over time (Line Chart).

- Ranking (Clustered Bar Chart).

- Flow (Waterfall Chart).

- Part-to-Whole (Clustered Bar Chart).

- Distribution (Clustered Column).

- Correlation (Scatterplot).

</br>

### **Interpreting Descriptive Statistics:**

For a quick refresher you can complete [the following course](https://www.khanacademy.org/math/statistics-probability).

- Variance (Variability / Spread of distribution).

- Effect Size (Difference between groups).

- PMF (Used to calculate the mean and variance of the discrete distribution).

- CDF (Obtained by summing up the probability density function and getting the cumulative probability for a random variable).

- Different Distributions (Gaussian, Log Normal, Pareto).

- PDF (Statistical expression that defines a probability distribution (the likelihood of an outcome) for a discrete random variable (e.g., a stock or ETF).

- KDE (Application of kernel smoothing for probability density estimation).

- Raw Moment vs Standardized Moment (moment that is not normalized vs normalized).

- Correlation Methods (Spearmans vs Pearsons).

- Other terms to know (Standard Error, Chi Squared Tests).

*To learn more and apply basic stats required for the exam try [this repository book](https://github.com/AllenDowney/ThinkStats2)*.

</br>

### **Interpreting OLS-Stats Summary:**

When running an ordinary least squared

- Dep Variable (What we are trying to predict).

- Model (Usually OLS).

- Number of Observations.

- DF Residuals (Degrees of Freedom -> nr of observations - predicted variable - 1).

- DF Model (Predicted Variables).

- Covariance (Type -> Positive / Negative)

- R Squared &rarr; How much the independent variable is explained by changes in dependent variables.

- Adjusted R Squared &rarr; Penalizes for non-contributing variables.

- F-Stat &rarr; Finds out if variables are statistically significant.

- Coef &rarr; Positive or inverse relationship of the dependent to the independent variable.

- Std Error &rarr; Std of Coef &rarr; Variation of Coefficient.

- p|t| &rarr; Uses t-stat to produce p-value (showing statistical significance).

- Omnibus &rarr; Normalcy of distribution using skwe and curtosis as measurements (0 = perfectly normal).

- Prob (Omnibus) &rarr; Probability of residuals being normally distributed.

- Skew &rarr; Symmetry (0 = Perfect symmetry).

- Kurtosis &rarr; (High = Few Outliers).

- Durbin Watson &rarr; [1-2] is the best range for homoscedasticity.

- JB &rarr; Alternative method of measuring normalcy of distribution.

- Condition Number &rarr; Measures multicollinearity 

*To learn more about OLS and stats models library interpretation for the exam read [this article](https://medium.com/swlh/interpreting-linear-regression-through-statsmodels-summary-4796d359035a)*.

- P-value &rarr; determines how likely is it that data could have occured under null hypothesis by random chance (Lower than 0.05 we reject null and count it as significant).

</br>

------

</br>

## **Domain 3: Modeling**

</br>

### **When to use ML/AI:**

- When we have the right amount of data (and the right data).

- Properly have assessed the ROI and similar use cases.

- Ease of support and deployment.

- Team support (Devs, Product, DevOps).

### **Supervised vs Unsupervised Learning**

- Supervised &rarr; has labeled inputs and outputs.

  - Classification (Linear Classifiers, SVM, Decision Trees, Random Forests).

  - Regression (Linear Regression, Logistic, Polynomial).

- Unsupervised (Clustering Unlabeled Data).

  - Clustering (K-Means &rarr; Grouping on Similarities).

  - Association (F.ex Recommenders).

  - Dimensionality Reduction (Autoencoders / PCA).

- Other differences:

  - Goals (Supervised &rarr; Prediction, Unsuppervised &rarr; Need to make sense).

  - Application (Supervised &rarr; Sentiment/Forecasting, Unsupervised &rarr; Recommenders).

  - Complexity (May vary).

  - Drawbacks (Time, accuracy, domain expertise).

- Semi-Supervised difference:

  - A mix of both methods

  - Uses labeled data for ground predictions & unlabeled data to learn shape of distribution.

  - Self-training (Modifying supervised training to work in semi-supervised way).

  - Use case: Ranking web pages (Google).

### **Selecting Appropriate Model**

Note: Here we are only including some of the main ML/DL models. There are many more which we can find on sites such as hugging face, connected papers etc.

We need to decide based on:

- Regression vs Classification

- Type of data

- Scope / Objective

### **[XGBoost](https://www.youtube.com/watch?v=OtD8wVaFm6E)**

- Tree based model in adjusting weights of weak vs strong learners.

- We use it when:

  - We have large number of observations in training data.

  - Nr. of observations > Nr. of features.

  - Mixture of numeric & categorical (or just numeric).

  - Used for supervised problems.

### **[Logistic Regression](https://youtu.be/yIYKR4sgzI8)**

- Simple algorithm for classifying categorical data.

- Examples include Spam detection etc.

### **[K-Means](https://www.youtube.com/watch?v=4b5d3muPQmA)**

- Mean of clustered data points is at minimum / per cluster.

- We use it when:

  - We dont have specific outcome to predict.

  - Unsupervised problem (lacking labels).

### **[Linear Regression](https://www.youtube.com/watch?v=nk2CQITm_eo&list=PLblh5JKOoLUIzaEkCLIUxQFjPIlapw8nU)**

- Adjusting and assessing relationship of variables

- Use when we want to predict outcome of target variable based on the relationship predictor variables.

- A simple checklist to check whether the model is appropriate is the following:

  - Check for a linear relationship of variables.

  - Multivariate normality (close to normal distribution).

  - No multicollinearity (correlation of independent variables).

  - Autocorrelation kept to a minimum (similarity of lagged version with itself).

  - Homoscedasticity (constant variance of error term).

### **[Decision Trees](https://youtu.be/_L39rN6gz7Y)**

- Simple algorithm based on decision for each leaf.

- We can use them when we want easier interpretation (instead of Random Forests).

- Can be used both for regression & classification.

### **[Recurrent Neural Networks (RNNs)](https://youtu.be/AsNTP8Kwu80)**

- Neural networks where output from previous step is fed to current input.

- Mainly used for text, speech and generative AI.

### **[Convolutional Neural Networks (CNNs)](https://youtu.be/HGwBXDKFk9I)**

- Use convolution to extract features.

- Has connected layers to make final prediciton.

- Main use: facial recognition, self-driving cars etc.

### **[Transfer Learning](https://youtu.be/yofjFQddwHE)**

- Storing knowledge from previous task to a new taks (f.ex vehicle to bus recognition).

### **Train/Test/Validation and Cross Validation**

- Rule of thumb:

  - Training data > 1000k

  - Best train/test/split usually around 75/10/15 (Adjusted on variance, data size etc.).

- Cross Validation Steps:

  - Shuffle dataset randomly.

  - Split in k groups.

  - Take holdout (test/training).

  - Fit Model.

  - Summarize skill of model.

- Cross Validation types:

  - Leave-p-out (Using p for validation).

  - Leave-one-out (p=1).

  - Stratified k-fold (good for imbalanced sets, but not time series).

  - Time Series.

  - Nested (Double CV).

### **[Other Important Concepts](https://www.analyticsvidhya.com/blog/2021/10/a-comprehensive-guide-on-deep-learning-optimizers/)**

- Loss Functions (Display whether models show improvement).

- Squared Error (Square of difference between actual and predicted values).

- Gradient Descent (Optimization algorithm where multiple epochs adjust with changing weights to find local/global minima).

  - Batch/Vanilla (Takes all available training data to find minima) - but its too slow.

  - Stochastic (Shuffles and constantly aims for new minima) - good, but still slow.

  - Mini-Batch (Less than total data sets) - here optimizers come in.

- Types of optimizers:

  - Momentum &rarr; weight parameters updated through previous gradient based on momentum.

  - AdaGrad &rarr; suited for sparse data / adjust properly weights manually.

  - RMSProp &rarr; Better than AdaGrad since adjusts weights automatically faster.

  - Adam &rarr; exploits momentum speed while exponentially decaying average of past grad

### **CPU vs GPU**

- CPU better choice for general, non-DL, small data cases.

- GPU for data with huge volume, Deep Learning.

### **Distributed vs Non-Distributed ML**

- We should not use SPARK or equivalent solution if:

  - processing pandas time is reasonable.

  - we dont need all data to be processed.

  - we have equivalent solution in cloud (EMR).

  - solution can be implemented with simple SQL.

### **Hyper Parameter Optimization**

- [Regularization](https://www.einfochips.com/blog/regularization-make-your-machine-learning-algorithms-learn-not-memorize/) (Prevents a model from overfitting through regularizing learning).

- 3 main regularization methods:

  - Ridge Regression (L2 Regularization)
  
    - Add the sum of weight’s square to a loss function and thus create a new loss function which is denoted thus

    ![L2](https://www.einfochips.com/blog/wp-content/uploads/2019/01/L2-Regularization.png)

  - Lasso Regression (L1 Regularization)

    - Uses absolute weight values for normalization

    - Eliminates less important features and sets respective weight values to zero  performing feature selection along with regularization.

    - ![Lasso](https://www.einfochips.com/blog/wp-content/uploads/2019/01/L1-Regularization.png)

  - Dropout (Mainly for Neural Nets)

    - Drop connections with 1-p probability for each of the specified layers. Where p is called **keep probability parameter** and which needs to be tuned.

    - ![Dropout](https://www.einfochips.com/blog/wp-content/uploads/2019/01/Dropout.png)


### **[Hyperparameter Tuning](https://neptune.ai/blog/hyperparameter-tuning-in-python-complete-guide)**

- Hyperparameter tuning determines the right combination of hyperparameters that maximizes the model performance.

- Main Hyperparameter tuning methods:

  - GridSearchCV (a grid of possible values tried in order). Very slow, but the best performing.

  - RandomizedSearchCV (grid of possible values for hyperparameters but each iteration tries a random combination of hyperparameters from this grid). Faster, but lower accuracy.

  - BayesSearchCV (uses bayesian algorithm to find the minimal point in the minimum number of steps.). Faster than GridSearch & produces better results than RandomizedSearch.


### **[Neural Networks in High Level](https://youtu.be/aircAruvnKk)**

Basic idea is to think in term of brain synapses and how they transmit information.

For neural nets we use various formulas to adjust the layers in which we transmit the information. 

![Brain](https://miro.medium.com/max/640/1*Zx0FP-qA_mlAWqxiQh7ZRw.webp)

![Neuron](https://miro.medium.com/max/640/1*39ZfHWfdv1UNhFFS9dcb1Q.webp)

*Note: Watch and keep notes of the 3B1B Neural Network [playlist here](https://youtu.be/aircAruvnKk)*.

### **Evaluating Machine Learning Models**

Overfitting & Underfitting in a nutshell!

![Over&Under](https://miro.medium.com/max/720/1*lARssDbZVTvk4S-Dk1g-eA.webp)

- [Avoiding overfitting](https://elitedatascience.com/overfitting-in-machine-learning):

  - Use Cross-Validation.

  - ![CV](https://elitedatascience.com/wp-content/uploads/2017/06/Cross-Validation-Diagram-768x295.jpg)

  - Train more data.

  - Early stopping algorithm.

  - ![Stop](https://elitedatascience.com/wp-content/uploads/2017/09/early-stopping-graphic.jpg)

  - Adjust Regularization.

  - Ensemble models (F.ex Bagging & Boosting)

- Avoid Underfitting (Adjust the abovementioned, but on the opposite end).

  - Decrease regularization

  - Increase the duration of training

  - Increase the model complexity (Parameters f.ex)

  - Shuffling data after each epoch (Neural Nets).

### **[Main Metrics](https://neptune.ai/blog/performance-metrics-in-machine-learning-complete-guide)**

### **Regression Metrics**

- **Mean Squared Error (MSE)**

  - Average of the squared difference between the target value and the value predicted.

  - Penalizes small errors. Due to the squaring, it’s more prone to outliers than other metrics. Overstimates errors.

  - ![MSE](https://lh5.googleusercontent.com/UU0UymvLgNfq6va2--cOndvalbdcZQX20FuzalU2RR0qxwesRa2pjZesapeFvMnRu39KlVbGIhVk6W6w1C2o_WbwEOYoU9UZtnZCw2eS2hBQbR-4RSShqkMGGCfg9Lr3eVM_1e-8)

- **Mean Absolute Error (MAE)**

  - Average of the difference between the ground truth and the predicted values.

  - MAE uses absolute value of the residual (doesnt overestimate errors. However, it doesn’t give us an idea of the direction of the error).
  
  - ![MAE](https://lh6.googleusercontent.com/gbSihak-qx9VaNa-ibUqxaIM6mD9nmfwI7wwxK_tRyOfUUGJ_XnH6jU_vcDqD9IgI1disL-cTIELJx5skJZ2uIX6oSC9rG2M8hKoabc4fIoBzJdNg3NkT91GBqH9yabg5sKSf4-J)

- **Root Mean Squared Error (RMSE)**

  - Square root of the average of the squared difference between the target value and the value predicted - SQRT(MSE)

  - Best of both worlds since its differentiable (like MSE) and less prone to outliers (like MAE).
  
  - ![RMSE](https://lh5.googleusercontent.com/pxb5gFdX2WYgW5dAvofM3bGUpJumpr_ATYdTScT3oXB-fXr-wAZ4QTOEjNaWpDtVPyU_Iyv62uJ3HlzAcT6dVj9x5ZgZ246oCgD5zVVOW65EQ8XUnESmVVHRLt7sc5szK4pIXxC_)

- **R-Squared (R²)**

  - Post-metric: How much (what %) of the total variation in Y(target) is explained by the variation in X(regression line). 

  - If the sum of Squared Error of the regression line is small => R² will be close to 1 (Ideal), meaning the regression was able to capture 100% of the variance in the target variable.
  
- **Adjusted R-Squared (Adj-R²)**

  - R² can mislead (showing improvement when really we are overfitting).

  - Adj-R² is adjusted with the number of independent variables.
  
  - Adjusts for the increasing predictors and only shows improvement if there is a real improvement.
  
  - ![RMSE](https://lh3.googleusercontent.com/D3TyYb1YNZKngK6sE01edMDL0u0uyJDlaaiwXu0g9haVWxJ9hqC3T01RUGTqPqelUIgIfBKI_KBAd8NyRVORsRKXmikIOJjv-MMgeka8fRHYNBW5vrVU15wrMTVgsdUrScthMACf)

### **Classification Metrics**

- **Accuracy**

  - Number of correct predictions divided by the total number of predictions, multiplied by 100.

  - Simplest model (not many insights on distribution or breakdown).

- **Confusion Matrix**

  - Tabular representation of ground-truth labels versus model predictions.

  - First we raise a hypothesis &rarr; then decide on True / False labels as below.
  
  - ![Confusion Matrix](https://lh5.googleusercontent.com/Zc7lXIYu0XBJG-P_VWLhiyAmWTvUL-CPLcRxiNnJy03JPoIPkJWmdGn4kxFdm6I0MBDBr7tlZW6Wlko5aO--eleGQQoy3yKQJcGSapDRqCf-W3xxiFjnGzNQXBzaHDK-y32lVUvr)

  - The components on a confusion matrix are the following:

    - True Positive(TP) number of positive class samples model predicted correctly.

    - True Negative(TN) number of negative class samples model predicted correctly.

    - False Positive(FP) number of positive class samples your model predicted incorrectly (Type-I error).

    - False Negative(FN) number of negative class samples your model predicted incorrectly (Type-II error).

  - Core formulas we need to know are the following:

    - Precision &rarr; ratio of true positives to total positives predicted.

    - The close to 1, the better (>0.5 as starting point).

    - ![Precision](https://i0.wp.com/neptune.ai/wp-content/uploads/2022/10/Performance-metrics-precision.png?ssl=1)

    - Recall &rarr; ratio of true positives to all the positives.

    - The close to 1, the better (>0.5 as starting point).

    - Summary of confusion matrix breakdown:

    - ![Summary](https://www.researchgate.net/publication/336402347/figure/fig3/AS:812472659349505@1570719985505/Calculation-of-Precision-Recall-and-Accuracy-in-the-confusion-matrix.ppm)

- **F1-score**

  - Harmonic mean of precision & recall.

  - High score &rarr; shows good balance between precision and recall and gives good results on imbalanced classification problems.

  - ![F1](https://lh6.googleusercontent.com/GJd7fTEzlzcUW1z3q7KJrk5FIUwZYnSqIQ-iqejGCR2ANqdUDcvj0bhhvaSI4yfBE0bFDqdNimzRetBO5NL9fljZ0kO-BniYC5U3M_l3nJw2OORUzW6i8w6_iCjXDpyDHenIpi7Z)

- **AUC-ROC (Area under Receiver operating characteristics curve)**

  - Area under the curve between combination of Recall (TPR) & Fallout (FPR) - also knows as ROC.

  - The bigger the area (extending on upper-left corner) the better results.

  - ![ROC](https://developers.google.com/static/machine-learning/crash-course/images/ROCCurve.svg)

  - ![ROC](https://developers.google.com/static/machine-learning/crash-course/images/AUC.svg)

### **Clustering Evaluation**

- **Dunn Index**

  - Identifies clusters that have low variance and are compact. The mean values of the different clusters also need to be far apart.

  - High computational cost with high number of clusters

  - ![Dunn](https://cdn.analyticsvidhya.com/wp-content/uploads/2019/08/Screenshot-from-2019-08-08-15-37-22.png)

- Silhouette Coefficient

  - Tracks how every point in one cluster is close to every point in the other clusters in the range of -1 to +1

  - A score of 1 denotes the best (meaning that the data point i is very compact within the cluster to which it belongs and far away from the other clusters).

  - ![Silhouette](https://editor.analyticsvidhya.com/uploads/59928Untitled.png)

- Elbow Method

  - Determine the number of clusters in a dataset by plotting the number of clusters on the x-axis against the percentage of variance explained on the y-axis.

  - Basically find sweet spot between nr. of clusters & variance (as below):

  - ![Elbow](https://i0.wp.com/neptune.ai/wp-content/uploads/2022/10/clusters.png?ssl=1)
  
  - **Simple summary of bias / variance tradeoff**
    - ![tradeoff](https://miro.medium.com/max/720/1*wPUGn4buYw4LYISGL-TUuA.webp)

**For A/B Testing read the [following article](https://towardsdatascience.com/25-a-b-testing-concepts-interview-cheat-sheet-c998a501f911) for better understanding**

*For deeper understanding on evaluating machine learning models for business use cases, I highly recommend **[this book](https://www.amazon.sg/Data-Science-Business-Data-Analytic-Thinking/dp/1449361323/ref=asc_df_1449361323/?tag=googleshoppin-22&linkCode=df0&hvadid=389114203157&hvpos=&hvnetw=g&hvrand=9338476164786084356&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9062524&hvtargid=pla-448095044074&psc=1)** as a reading complementary resource. **Warning**: Dont use [this source](https://libgen.is/) for it ;)!

</br>

------

</br>

## **Domain 4: Machine Learning Implementation and Operations**

### The following seminars offer an overview on the best patterns to follow for productionizing machine learning

</br>

1. **[End to End - MLOps Architecture Patterns](https://youtu.be/UnAN35gu3Rw)**

- The typical data scientist setup **(which is bad)** is the following:

  - Data Sources (S3, EFS, RDS, DynamoDB, Redshift, EMR etc).

  - Sagemaker notebooks (getting data from the sources).

  - Storing in S3 model artifacts (output, files etc).

  - Sagemaker Endpoint (make real-time inferences via a REST API).

  - Create Lambda function to connect through API Gateway.

  **This setup is bad since:**

    a.  We have to manually re-run cells.

    b.  Code is stuck in notebooks (difficult to version & automate).

    c. No autoscaling or feedback.

</br>

- **INSTEAD WE CREATE THE FOLLOWING**:

- **


2. **[Automate MLOps with SageMaker Projects](https://youtu.be/3_cHnk9VSfQ)**

3. **[How to productionize ML workloads at scale](https://youtu.be/fJer8dO3iFU)**

4. **[]

