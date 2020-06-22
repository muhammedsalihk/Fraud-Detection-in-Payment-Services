# Fraud Detection in Payment Services

## Introduction
In the financial services sector, fraud prevention is a very important facet of its business owing to the scale of annual loss it can lead to in addition to the damage in reputations and customer confidence.

In this project, we are trying to build a fraud prevention system for a mobile payments service using the XGBoost library.

## Data Description
The dataset contains 10 features which includes some the type of transaction, information on the origin and destination account balances, the transaction amount, time of transaction etc. This is a synthetic data set developed by E. A. Lopez-Rojas , A. Elmir, and S. Axelsson as part of the research project ”Scalable resource-efficient systems for big data analytics”.

![Initial DF](https://github.com/muhammedsalihk/Fraud-Detection-in-Payment-Services/blob/master/Images/Initial%20DF.png)

The dataset contains more than 6 million transaction records. The dataset is highly imbalanced and only 0.13% of the transactions are fraudulent.

## Methodology
To tackle the imbalance problem, an undersampling technique was tried out and it gave good results.

Before going ahead with the sampling, a detailed exploratory analysis was perfomed on the data and based on the inferences obtained, a set of relevant features were selected and some new features were engineered.

![Final DF](https://github.com/muhammedsalihk/Fraud-Detection-in-Payment-Services/blob/master/Images/final%20DF.png)

The data was divided into three sets (train, dev and test) in an 90-5-5 ratio. We had to define an explicit dev set as cross validation approach on the train set wouldn’t be viable while using the undersampling and oversampling techniques as the train set in those cases wouldn’t exactly represent the real world case.

The evaluation metric used for determining the performance of the models was F1 score. Accuracy, although very intuitive, couldn’t be employed owing the to the imbalance in the dataset.

## Results
The modelling was done using XGBoost and the dev set was used to tune the hyperparameters. Owing to the engineering of a new features that were highly indicative of fraud, a high performing model could be developed.

An **F1 score of 0.9987** was obtained on the test set using the developed model.
