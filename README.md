# Credit Risk Analysis

## Overview of the Analysis

The purpose of this analysis was to evaluate and predict individual customer credit risk using Supervised Machine Learning algorithms. Since credit risk is an inherently unbalanced classification problem, where good loans easily outnumber risky loans, a variety of machine learning algorithms was used to predict credit risk, such as,

**Resampling Techniques**
* Naive Random OverSampling
* SMOTE Oversampling 
* Cluster Centroids Undersampling
* SMOTEENN (Combination of Over and Under Sampling)

**Ensemble Learning Technique**
* Balanced Random Forest Classifier
* Easy Ensemble AdaBoost Classifier

In the Naive Random OverSampling and SMOTE algorithms, the data was oversampled, and in Cluster Centroids algorithm, the data was undersampled. In SMOTEENN algorithm a combination of over- and undersampling was used. The details of the analysis can be found in the code, [credit_risk_resampling.ipynb]. A comparison between two new machine learning models that reduce bias, Balanced RandomForest Classifier and Easy Ensemble Classifier, was made to predict credit risk. The details of this analysis can be found in the code, [credit_risk_ensemble.ipynb](https://github.com/dshetty100/Credit_Risk_Analysis/blob/main/credit_risk_ensemble.ipynb)

The models were run and then evaluated for performance and accuracy at predicting credit risk.

The analysis was performed using imbalanced-learn and scikit-learn libraries to train and evaluate the models. The credit card credit dataset (LoanStats_2019Q1) from LendingClub, a peer-to-peer lending services company, was utilised for the analysis. After cleaning the data, the dataset consisted of 68,470 entries, and was heavily unbalanced, with only 0.5% of entries being classified as "high-risk."



## Results

The balanced accuracy scores and the precision and recall scores of all six machine learning models is discussed below.
The results are presented in ascending levels of performance, based on their balanced acuracy scores, starting with the worst-performing model and moving to the best.

* **Cluster Centroids Undersampling** gave us the worst results, with an accuracy score of 0.5295. That means that it did little better than 50%, or a 50/50 coin-toss, at accurately predicting credit risks.
    ![Cluster Centroids Undersampling Balanced Accuracy Score](Images/CC_BA.png)

    It's F-scores were similarly disappointing, achieving an average of only 0.56 and an F-score for high-risk prediction of only 0.01.
    ![Cluster Centroids Undersampling Imbalanced Classifications Report](Images/CC_CR.png)

* **Combination Sampling** gave us the second-worst results, with an accuracy score of 0.6529. That means that it did little better than 65%, or 2/3rds accuracy at predicting credit risks.
    ![Combination Sampling Balanced Accuracy Score](Images/SMOTEEN_BA.png)

    It's F-scores were still disappointing, achieving an average of only 0.72 and an F-score for high-risk prediction of only 0.02.
    ![Combination Sampling Imbalanced Classifications Report](Images/SMOTEEN_CR.png)

* **SMOTE Oversampling** gave us the third-worst results, with an accuracy score of 0.662. This is about the same performance we saw from **Combination Sampling**. This means that it did little better than 66%, or 2/3rds accuracy at predicting credit risks.
    ![SMOTE Oversampling Balanced Accuracy Score](Images/SMOTE_BA.png)

    It's F-scores showed were also disappointing, achieving only a marginally improved average of 0.80 and another F-score for high-risk prediction of only 0.02.
    ![SMOTE Oversampling Imbalanced Classifications Report](Images/SMOTE_CR.png)

* **Naive Random Oversampling** brings us to the midway point in our model performances. The ROS model gave us the third-best results, with an accuracy score of 0.6732. This is still about the same performance we saw from **Combination Sampling** and **SMOTE Oversampling**. This means that it did little better than 67%, or 2/3rds accuracy at predicting credit risks.
    ![Random Oversampling Balanced Accuracy Score](Images/NRO_BA.png)

    It's F-scores were also worse or on-par with **SMOTE Oversampling**. The ROS model achieved an average of 0.76 and another F-score for high-risk prediction of only 0.02.
    ![Random Oversampling Imbalanced Classifications Report](Images/NRO_CR.png)

* **Balanced Random Forest Classifier** gave us the second-best results, showing marked improvement with an accuracy score of 0.7615. However, this is still far from perfect. This means that it could only accurately predict about 76%, or 3/4ths of the appropriate levels of credit risks.
    ![Balanced Random Forest Classifier Balanced Accuracy Score](Images/BRFC_BA.png)

    It's F-scores were where there was most improvement (relatively). The BRFC model achieved an average F-score of 0.92, which is at least in the 90's. However, it's F-score for high-risk prediction was still low, at only 0.06.    
    ![Balanced Random Forest Classifier Imbalanced Classifications Report](Images/BRFC_CR.png)

* **Easy Ensemble AdaBoost Classifier** was the best-performing model, hands-down. It's results were leagues beyond all other models attempted. It gave us an accuracy score of 0.9319. While not perfect, this means that it could accurately predict at a rate greater than 93% of the appropriate levels of credit risks.
    ![Easy Ensemble AdaBoost Classifier Balanced Accuracy Score](Images/EEAC_BA.png)

    It's F-scores were also fairly impressive. The EEC model achieved an average F-score of 0.97. However, while the best performing, it's F-score for high-risk prediction was still low, at only 0.16.      
    ![Easy Ensemble AdaBoost Classifier Imbalanced Classifications Report](Images/EEAC_CR.png)

## Summary
In conclusion, credit-risk is a difficult thing to predict, even for advanced machine learning algorithms with 93 columns of data to process. While the **Easy Ensemble AdaBoost Classifier** model had the highest overall accuracy, this was largely due to the fact that the dataset was so radically unbalanced. Even when it's balanced accuracy and average F-score were above 90%, it's F-score for high-risk prediction was no better than 0.16. In the end, I would advise against using any of these algorithms, as it would put creditors as too great of risk being unable to accurately predict who the high-risk clients/debtors would be.