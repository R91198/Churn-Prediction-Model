We started with the EDA process. We examined the relation of the target variables with few of the key features like Customer_status, ActiveSinceDays etc. This gave us some key insights that helped us zero in on our feature engineering strategy.
During the feature engineering our focus was to create columns that would unearth the customer’s transactional behavior over the last 3 months. Also, we created columns that were based on aggregations of the customer status behavior.
There were 6 columns with missing values. We used the Robust Scaler, which works on scaling using the interquartile range, hence not heavily influenced by the presence of outliers. After we scaled the data, we used the mean to fill in the missing values.
Next we dropped columns with correlation > 0.75.
We started with a simple Logistic Regression model, that gave us the Area Under the curve of 0.52.
Then we addressed the class imbalance (not a major class imbalance) problem using synthetic minority oversampling (SMOTE). Post smote the Logistic Regression model gave us an AUC of 0.63.
Since the class imbalance problem is taken care of, we can focus on the AUC metric.
Then we used the recursive feature elimination method, which increased our AUC to 0.78. 
This was followed by using KNN and Random Forest, which had scores of 0.76 & 0.78 respectively.
Then we used the Hyperopt library to find the best parameters for our XGBoost model.
With the  parameters obtained using the Hyperopt process, our XGBoost model gave us an AUC score of 0.99
