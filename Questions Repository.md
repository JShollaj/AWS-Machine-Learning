# List of Potential Questions

This is a list of all questions I could gather from all the sources I used. You can DM me for the solutions.

---

1. A data engineer needs to create a cost-effective data pipeline solution that ingests unstructured data from various sources and stores it for downstream analytics applications and ML. The solution should include a data store where the processed data is highly available for at least one year, so that data analysts and data scientists can run analytics and ML workloads on the most recent data. For compliance reasons, the solution should include both processed and raw data. The raw data does not need to be accessed regularly, but when needed, should be accessible within 24 hours.

   **What solution should the data engineer deploy?**

</br>

2. An ad-tech company has hired a data engineer to create and maintain a machine learning pipeline for its clickstream data. The data will be gathered from various sources, including on premises, and will need to be streamed to the company’s Amazon EMR instances for further processing.

   **What service or combination of services can the company use to meet these requirements?**

</br>

3. A healthcare company using the AWS Cloud has access to a variety of data types, including raw and preprocessed data. The company wants to start using this data for its ML pipeline, but also wants to make sure the data is highly available and located in a centralized repository.

   **What approach should the company take to achieve the desired outcome?**

</br>

4. A Data Scientist wants to implement a near-real-time anomaly detection solution for routine machine maintenance. The data is currently streamed from connected devices by AWS IoT to an Amazon S3 bucket and then sent downstream for further processing in a real-time dashboard.

   **What service can the Data Scientist use to achieve the desired outcome with minimal change to the pipeline?**

</br>

5. A transportation company currently uses Amazon EMR with Apache Spark for some of its data transformation workloads. It transforms columns of geographical data (like latitudes and longitudes) and adds columns to segment the data into different clusters per city to attain additional features for the k-nearest neighbors algorithm being used.

   The company wants less operational overhead for their transformation pipeline. They want a new solution that does not make significant changes to the current pipeline and only requires minimal management.

    **What AWS services should the company use to build this new pipeline?**

</br>

6. A team of data scientists in a company focusing on security and smart home devices created an ML model that can classify guest types at a front door using a video doorbell. The team is getting an accuracy of 96.23% on the validation dataset.

   However, when the team tested this model in production, images were classified with a much lower accuracy. That was due to weather: The changing seasons had an impact on the quality of production images.

    **What can the team do to improve their model?**

</br>

7. A team of data scientists in a financial company wants to predict the risk for their incoming customer loan applications. The team has decided to do this by applying the XGBoost algorithm, which will predict the probability that a customer will default on a loan. In order to create this solution, the team wants to first merge the customer application data with demographic and location data before feeding it into the model.

   However, the dimension of this data is really large, and the team wants to keep only those features that are the most relevant to the prediction.

    **What techniques can the team use to reach the goal?**

</br>

8. A Machine Learning Engineer is creating and preparing data for a linear regression model. However, while preparing the data, the Engineer notices that about 20% of the numerical data contains missing values in the same two columns. The shape of the data is 500 rows by 4 columns, including the target column.

   **How could the Engineer handle the missing values in the data?**

</br>

9. A social networking organization wants to analyze all the comments and likes from its users to flag offensive language on the site. The organization’s data science team wants to use a Long Short-term Memory (LSTM) architecture to classify the raw sentences from the comments into one of two categories: offensive and non-offensive.

   **What should the team do to prepare the data for the LSTM?**

</br>

10. A Data Scientist created a correlation matrix between nine variables and the target variable. The correlation coefficient between two of the numerical variables, variable 1 and variable 5, is -0.95.

    **How should the Data Scientist interpret the correlation coefficient?**

</br>

11. An oil and natural gas company is using machine learning to discover prime locations for drilling. The company has chosen Amazon SageMaker as its service for creating machine learning models. The company’s data scientists are using notebook instances to develop those models. However, the data scientists spend a long time waiting for the training jobs to complete.

     The company wants improve this idle time to more effectively iterate on the models with minimal change to the code to enable data scientists to quickly experiment with their models without having to wait for the training job to load the data and train the model.

      **What should the team of data scientists do to solve this issue?**

</br>

12. A data scientist trained an XGBoost model to classify internal documents for further inquiry, and now wants to evaluate the model’s performance by looking at the results visually.

      **What technique should the data scientist use in this situation?**

</br>

13. A real estate company wants to provide its customers with a more accurate prediction of the final sale price for houses they are considering in various cities. To do this, the company wants to use a fully connected neural network trained on data from the previous ten years of home sales, as well as other features.

      **What kind of machine learning problem does this situation represent?**

</br>

14. A manufacturing company wants to increase the longevity of its factory machines by predicting when a machine part is about to stop working, jeopardizing the health of the machine. The company’s team of Data Scientists will build an ML model to accomplish this goal. The model will be trained on data made up of consumption metrics from similar factory machines, and will span a time frame from one hour before a machine part broke down to five minutes after the part degraded.

      **What kind of machine learning algorithm should the company use to build this model?**

</br>

15. A Data Scientist working for an autonomous vehicle company is building an ML model to detect and label people and various objects (for instance, cars and traffic signs) that may be encountered on a street. The Data Scientist has a dataset made up of labeled images, which will be used to train their machine learning model.

      **What kind of ML algorithm should be used?**

</br>



