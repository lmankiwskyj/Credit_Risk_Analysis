# Credit_Risk_Analysis

## Overview 
With the credit dataset from LendingClub machine learning models were tested to determine which is better at predicting credit risk.  Credit risk is an inherently unbalanced classification problem, meaning, the distribution of examples across the known classes is skewed (good loans outnumber risky loans).  Imbalanced classifications pose a challenge for predictive modeling as most of the machine learning algorithms used for classification were designed around the assumption of an equal number of examples for each class. Therefore, different techniques to train and evaluate models were used; resampling and ensemble classifiers.

## Results
To review the results of each model, we'll be looking to answer the question, how well does it perform? 
   - An accuracy score is one way of assessing a classification model's performance, this tells us what percentage of predictions does it get right.  It is defined as the    
      average of recall obtained on each class, the best value is 1 and the worst value is 0.  
   - Another way to review the model's performance is precision.  The test results are collated into a table, called a confusion matrix.  This shows what is actually true and  
      predicted as true by the model (true positive), actually true and predicted as false (false positive), actually true, but predeicded as false (false negaive), and what is 
      acutally false and predicted to be false (true negaitve).  Precision is obtained by dividing the number of true positives (TP) by the number of all positives (the sum of 
      true positives and false positives, or TP + FP).  
   - Sensitivity 
      or recall score is another way to assess a model's performance.  Sensitivity is a measure of the number of true positives (TP) plus the number of false negatives divided 
      by the number of true positives.  Highly sensitive tests and algorithms do a good job of detecting the intended targets, but also risk resulting in a number of false 
      positives. On the other hand, in high precision, there could be predicted positives that are likely true positives; but a number of other true positives may not be 
      predicted. 

### Resampling 
#### RandomOverSampler
Using the naive random oversampling algorithm to oversample the data using RandomOverSampler from the Inbalenced Learn library, the following results were collected:
  ##### Balanced Accuracy Score = 65%
  ##### Precision Score/Confusion Matrix
![Capture1](https://user-images.githubusercontent.com/90974647/151728099-2b898c5b-f8d7-4ac1-8f46-168dd33d23ea.PNG)
  ##### Recall Score/Imbalanced Classification Report
![Capture2](https://user-images.githubusercontent.com/90974647/151728057-425edb48-ffd1-41f4-b2c5-b065b2026f88.PNG)

#### SMOTE
Using another over-sampling algorithm SMOTE also from the Inbalenced Learn library, the following results were collected:
  ##### Balanced Accuracy Score = 66%
  ##### Precision Score/Confusion Matrix
  ![Capture3](https://user-images.githubusercontent.com/90974647/151728514-48945927-097e-4173-988c-e39347a07f0d.PNG)
  ##### Recall Score/Imbalanced Classification Report
  ![Capture4](https://user-images.githubusercontent.com/90974647/151728578-083192f9-1e4e-4b22-b15f-09bd8d28774f.PNG)

#### ClusterCentroids 
Using an under-sampling algorithm ClusterCentroids also from the Inbalenced Learn library, the following results were collected:
  ##### Balanced Accuracy Score = 66%
  ##### Precision Score/Confusion Matrix
  ![Capture5](https://user-images.githubusercontent.com/90974647/151728878-bfc51b07-0065-4d73-bf53-6b333d0945d5.PNG)
  ##### Recall Score/Imbalanced Classification Report
![Capture6](https://user-images.githubusercontent.com/90974647/151728940-6335a2bb-b395-418f-abbf-c1c020293dd7.PNG)

#### SMOTEENN
Using a combination over- and under-sampling algorithm SMOTEENN also from the Inbalenced Learn library, the following results were collected:
  ##### Balanced Accuracy Score = 54%
  ##### Precision Score/Confusion Matrix
![Capture7](https://user-images.githubusercontent.com/90974647/151729169-429ade02-30b2-45a7-90e0-c4df3165e125.PNG)
  ##### Recall Score/Imbalanced Classification Report
![Capture8](https://user-images.githubusercontent.com/90974647/151729214-cf6ae984-e3eb-4b11-b135-f82a898a8d5a.PNG)

### Ensemble Classifiers
#### Balanced Random Forest Classifier 
The Balanced Random Forest Classifier from the Inbalenced Learn library, randomly selects subsets of features used in each data sample.  Using this algorithm, the following results were collected:
  ##### Balanced Accuracy Score = 79%
  ##### Precision Score/Confusion Matrix
![Capture9](https://user-images.githubusercontent.com/90974647/151730391-d4555865-ba5f-437e-baec-73c85e236131.PNG)
  ##### Recall Score/Imbalanced Classification Report
![Capture10](https://user-images.githubusercontent.com/90974647/151730453-b2258715-e12b-4ebc-b47d-c3743a4067f1.PNG)

#### EasyEnsembleClassifier
Random under sampling with Adaptive Boosting, ensemble of AdaBoost Classifiers.  Using this algorithm, the following results were collected:
  ##### Balanced Accuracy Score = 93%
  ##### Precision Score/Confusion Matrix
![Capture11](https://user-images.githubusercontent.com/90974647/151732026-c75b8024-97be-4c41-9b75-d6ffe7ae62d1.PNG)
  ##### Recall Score/Imbalanced Classification Report
![Capture12](https://user-images.githubusercontent.com/90974647/151732053-91a2519b-10b5-47ac-ba79-9417cd623910.PNG)

## Summary
As you can see from the results above, the EasyEnsembleClassifier has the highest balanced accuracy score of 93%.  Along with the metrics of the minority class, precision ("pre"), and recall ("rec") are also improved over the other models used.  There is a trade-off between precision and recall and ultimately it is the cost of being wrong that will dictate the balance needed.  
