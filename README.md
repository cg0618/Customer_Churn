# <div align="center"> Telecom Customer Churn </div>

## Brief Introduction
Customer churn occurs when clients or subscribers cease their engagement or business relationship with a company or service provider.

The dataset contains churn data from a fictional telecommunications company. In the telecom industry, customers have the flexibility to select from a diverse range of service providers, often opting to switch between them. This dataset provides insights into customer behaviors and factors influencing churn within this highly competitive market.

The primary objective is to broaden coverage and enhance customer loyalty.

## Objectives
- To determine the percentage of customers who have churned and those who remain active with the services.
- To identify the most appropriate predictive model for accurately classifying customers into churned and non-churned categories.
- To examine the data with regard to different features influencing customer churn.

## The dataset
 [Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data)

### The dataset comprises data pertaining to:

- Customers who closed their contract/subscription in the past month, identified by the column labeled "Churn"
- Demographics – gender, age range, and if they have partners and dependents
- Information regarding customer accounts, such as their tenure, contract status, payment method, preference for paperless billing, monthly charges, and total charges.
- Services to which each customer has subscribed, which include phone, multiple lines, internet, online security, online backup, device protection, technical support, and streaming TV and movies.


## Exploratory Data Analysis (EDA)

### Demographics
#### 1. Senior Citizens and Dependents
Approximately only 16% of the customers are senior citizens. That is, majority of telecom customers are typically younger individuals who are not senior citizens. Additionally, a significant portion of these customers may not have dependents, suggesting that they are likely single or without immediate family responsibilities. This demographic profile can influence the telecom in tailoring their services and marketing strategies to provide the needs of this specific customer segment, such as focusing on features and plans that appeal to a younger, more independent audience.
>![seniorCitizen](https://github.com/cg0618/Customer_Churn/blob/main/images/seniorCitizen.png)
>![dependents](https://github.com/cg0618/Customer_Churn/blob/main/images/dependents.png)


#### 2. Phone Service and Internet service
The majority of customers have phone and internet services, illustrating a widespread reliance on telecommunications technology for both communication and online connectivity purposes.

>![PhoneService](https://github.com/cg0618/Customer_Churn/blob/main/images/PhoneService.png)
>![InternetService](https://github.com/cg0618/Customer_Churn/blob/main/images/InternetService.png)

#### 3. Online Security, Online Backup, and Device Protection
Most customers have chosen not to avail either online security, backup services or device protection, possibly influenced by concerns about additional charges. This decision may reflect prioritization of finances over enhanced protection and data backup.

>![OnlineSecurity](https://github.com/cg0618/Customer_Churn/blob/main/images/OnlineSecurity.png)
>![OnlineBackup](https://github.com/cg0618/Customer_Churn/blob/main/images/OnlineBackup.png)
>![DeviceProtection](https://github.com/cg0618/Customer_Churn/blob/main/images/DeviceProtection.png)


#### 4. TV and Movie Streaming 
The majority of customers are actively engaged in movie and TV streaming, which indicates that there is a significant preference for accessing entertainment content through digital platforms rather than traditional satellite television services. This trend emphasizes the increasing popularity and accessibility of streaming services in contemporary media consumption habits.

>![TVStreaming](https://github.com/cg0618/Customer_Churn/blob/main/images/StreamingTV.png)
>![MovieStreaming](https://github.com/cg0618/Customer_Churn/blob/main/images/StreamingMovies.png)

#### 5. Paperless Billing
Lots of customers are increasingly adopting paperless billing methods and are opting for digital payment options such as credit cards and other online payment methods. This trend suggests a growing preference for convenient and eco-friendly financial transactions in the digital age.
>![PaperlessBilling](https://github.com/cg0618/Customer_Churn/blob/main/images/PaperlessBilling.png)
>![PaymentMethod](https://github.com/cg0618/Customer_Churn/blob/main/images/PaymentMethod.png)


### Distribution of Total Charges by Churn
The boxplot below suggests that individuals categorized as Churners or Churned customers show smaller total charges in comparison to non-churners. Churners do not complete the contract, implying a likelihood of lower total charges compared to non-churners. To delve deeper into this data, the boxplot has been organized based on their respective contracts.

>![totChargeDist](https://github.com/cg0618/Customer_Churn/blob/80864801200b6f0ef3d111b7085468aab3041015/images/totChargeDist.png)

Surprisingly, it appears that customers with one-year and two-year contracts have higher total charges, which implies that different contract durations might contribute in influencing the total charges incurred by customers. Further, this means that after having their one-year and two-year contracts, customers are more likely to churn if they are having more total charge.

>![totChargeContractDist](https://github.com/cg0618/Customer_Churn/blob/80864801200b6f0ef3d111b7085468aab3041015/images/totChargeContractDist.png)

### Correlation
It seems that everything is normal because none of the factors are strongly correlated to the variable of interest, which is customer churn.

>![corr](https://github.com/cg0618/Customer_Churn/blob/c39c22721c280b2488a5a457fa8cdd5e4e0a3e51/images/corr.png)

### Histogram
Based on the histograms below, they suggest that customers are more inclined to churn when they are on a month-to-month contract. The histograms illustrate a higher frequency of customer churn within the month-to-month contract category compared to other contract types (One-year and Two-year contracts). This implies that there might be an association between the contract duration and customer churn, with a higher probability observed among those on a month-to-month arrangement.

>![histContTenure](https://github.com/cg0618/Customer_Churn/blob/3a78782251f7c214daaf4c1a74fd731a20bbca86/images/histContTenure.png)

## Predictive Modeling
- The data was standardized to address the limitations of machine learning algorithms. Standardization involves scaling the numerical features to a common scale, ensuring that they contribute equally to the model. 
- Due to an imbalance between customers who churn and those who don't, a technique called SMOTE (Synthetic Minority Over-sampling Technique) was utilized. SMOTE works by generating synthetic instances of the minority class (in this case, churners) to balance the class distribution. By creating these "realistic" data points, SMOTE helps the machine learning models better learn and generalize patterns from the imbalanced data, which enhances its ability to make accurate predictions on whether a customer is a churner or a non-churner.
- The dataset was divided into training and testing sets: 80% of the data was allocated for training the model and 20% was reserved for testing its performance. This approach helps evaluate how well the model generalizes to new, unseen data.

### 1. Logistic Regression Model

>The best parameters for LogisticRegression model is: {'C': 10, 'penalty': 'l2'}
>
>--------------------
>
>(R2 score) in the training set is 81.55% for LogisticRegression model.
>
>(R2 score) in the testing set is 82.38% for LogisticRegression model.
>
>F1 score is 0.83 for LogisticRegression model.


### 2. Support Vector Machine

>The best parameters for SVC model is: {'C': 1, 'gamma': 'scale'}
>
>--------------------
>(R2 score) in the training set is 83.16% for SVC model.
>
>(R2 score) in the testing set is 82.58% for SVC model.
>
>F1 score is 0.83 for SVC model.


### 3. Random Forest Classifier

>The best parameters for RandomForestClassifier model is: {'max_depth': None, 'n_estimators': 200}
>
>--------------------
>
>(R2 score) in the training set is 99.84% for RandomForestClassifier model.
>
>(R2 score) in the testing set is 85.14% for RandomForestClassifier model.
>
>F1 score is 0.85 for RandomForestClassifier model.

### Boosted Trees Classifier
### 4. AdaBoost Classifier

>The best parameters for AdaBoostClassifier model is: {'learning_rate': 0.2, 'n_estimators': 200}
>
>--------------------
>
>(R2 score) in the training set is 78.86% for AdaBoostClassifier model.
>
>(R2 score) in the testing set is 80.40% for AdaBoostClassifier model.
>
>F1 score is 0.81 for AdaBoostClassifier model.


### 5. Gradient Boosting Classifier

>The best parameters for GradientBoostingClassifier model is: {'learning_rate': 0.2, 'max_depth': 6, 'n_estimators': 100}
>
>--------------------
>
>(R2 score) in the training set is 94.71% for GradientBoostingClassifier model.
>
>(R2 score) in the testing set is 83.49% for GradientBoostingClassifier model.
>
>F1 score is 0.84 for GradientBoostingClassifier model.


### 6. XGBoost

>The best parameters for XGBClassifier model is: {'learning_rate': 0.2, 'max_depth': 5, 'n_estimators': 150}
>
>--------------------
>
>(R2 score) in the training set is 91.48% for XGBClassifier model.
>
>(R2 score) in the testing set is 84.51% for XGBClassifier model.
>
>F1 score is 0.85 for XGBClassifier model.


### 7. Multilayer Perceptron model

>--------------------
>
>(R2 score) in the training set is 82.27% for Multilayer Perceptron model.
>
>(R2 score) in the testing set is 82.67% for Multilayer Perceptron model.
>
>F1 score is 0.83 for Multilayer Perceptron model.


### 8. ANN with 2 hidden layers (ReLU activation)

>--------------------
>
>(R2 score) in the training set is 84.39% for ANN model.
>
>(R2 score) in the testing set is 82.09% for ANN model.
>
>F1 score is 0.83 for ANN model.


| Table | Train Score |	Test Score |	F1 Score |
| :---: | :---: |	:---: |	:---: |
|Logistic Reg|	0.8155|	0.8238|	0.8300|
|Decision Tree|	0.8316|	0.8258|	0.8300|
|Support Vector Machine|	0.8634|	0.8001|	0.8100|
|Random Forest|	0.9984|	0.8514|	0.8500|
|AdaBoost|	0.7886|	0.8040|	0.8040|
|Gradient Boosting|	0.9471|	0.8349|	0.8400|
|XGBoosting|	0.9148|	0.8451|	0.8500|
|Multilayer Perceptron|	0.8228|	0.8267|	0.8300|
|ANN|	0.8439|	0.8209|	0.8300|

## Conclusion
In summary, while the random forest model exhibited strong performance on the test set with a high F1 score, its apparent overfitting was indicated by the notably high training accuracy and a significant drop in performance when applied to the test set. Consequently, among the considered models, the XGBoost model emerged as the superior performer.
