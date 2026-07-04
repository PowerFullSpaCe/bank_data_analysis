# Data Analysis of a Bank Marketing Campaign 
## A project created during Data Mining and Machine Learning Module in R

This work utilizes classical machine learning and exploration approaches in order to predict whether a client will subscribe to a term deposit.

The project consists of the following sections:

1. __Exploratory data analysis__ - including the detection of multivariate outliers and anomalies;
2. __Data preprocessing__ - involving imputation, dimensionality reduction, feature selection and engineering, and class balancing.
   
   All preprocessing steps were standardized in order to ensure that multiple machine learning models could be trained and compared accurately on the exact same data.
   
   Furthermore, the dataset was split into training and testing sets using stratification. 5-fold cross-validation was also implemented to create consistent train/validation splits for each fold. This approach allows to accurately evaluate the model's true performance and generalization ability on the test dataset.
3. __Model building and training__
   
   To reduce computational cost, the ANOVA racing method was utilized to eliminate weak candidate models, combined with Latin Hypercube Sampling for hyperparameter optimization. The models where initially evaluated using ROC-AUC during cross-validation. After training, they were further compared using metrics such as recall, precision, PR-AUC, and F1-score. These metrics are appropriate here due to class imbalance and the importance of accurately distinguishing between the positive and negative classes.
   
   The Random Forest model performed relatively well, with its ROC-AUC being only 0.004 lower than that of XGBoost.
4. __Evaluation of the best model__

   XGBoost achieved the highest ROC-AUC score on this dataset and was therefore selected as the final model for evaluation on the test dataset. While there were no signs of overfitting, I could improve recall and precision by adjusting the classification threshold, which had previously been set set to the default value of 0.5 for all the trained models.
5. __Error and feature importance analysis__
   
   Reduced macroeconomic variables turned out to be the most significant factors in the XGBoost decision-making process. Whether a client had been contacted previously was also a strong indicator of their future behaviour. These insights could be leveraged to optimize future marketing campaigns.
   
All the details ycan be found in the source code and rendered HTML report.
