# Credit_Risk_Analysis

## Project Overview
A credit card risk evaluation program will be created using machine learning with `imbalanced-learn` and `scikit-learn` libraries. The project will demonstrate the affect different sampling techniques will have on a model.

Sampling techniques used will include:
- `RandomOverSampler` Oversampling
- `SMOTE` Oversampling 
- `Cluster Centroids` Undersampling
- `SMOTTEEN` Combinatorial
- `BalancedRandomForestClassifier` Ensemble
- `EasyEnsembleClassifiers` Ensemble

### Background information
A common issue in the machine learning domain is properly interpreting the model's metrics. When evaluating or 'screening' for rare occurences, where the classification of interest only amounts to a very small portion of the dataset, precision metrics can be very misleading. A popular example is where if 1 of 1,000,000 credit card transactions are fraudulent, a fake machine learning model that doesn't merely approves every single transaction would still have a a "Precision" of 99.9999%. An analyst must therefore understand the dataset, how the data will be used, and be knowledgeable about the metrics used to evaluate the model. In this example, of credit card risk, balanced accuracy score, recall and specificity will be more important that precision.


## Analysis/Machine Learning Results
The following sampling methods were all evaluated using the same machine learning model/algorithm:
`LogisticRegression(solver='lbfgs',random_state=1)`

|Sampling Method|Balanced Accuray Score|Confusion Matrix|Imablanced Classification Report|
|---|---|---|---|
|Random Oversampling|65.6%|![image](https://user-images.githubusercontent.com/79720695/129493402-a0e45ecc-1dea-4769-9365-57793795817b.png)|![image](https://user-images.githubusercontent.com/79720695/129493407-7e7984ed-29cb-4346-b05b-4d3122c12d74.png)|
|SMOTE Oversampling|63.6%|![image](https://user-images.githubusercontent.com/79720695/129493419-1420ac56-b348-41f8-9f4c-7b5ee69b58c2.png)|![image](https://user-images.githubusercontent.com/79720695/129493429-f61e2d26-ca0d-4cd7-8ac2-ba9f3b6ab8a2.png)|
|Central Centroid (Undersampling)|52.3%|![image](https://user-images.githubusercontent.com/79720695/129493441-0d0da9cb-3a9f-4acc-ba7a-b0f5b270bd05.png)|![image](https://user-images.githubusercontent.com/79720695/129493957-ec798e5a-6d9c-4546-90a1-96ec13b9ce39.png)|
|SMOTEENN (Combinatorial)|63.1%|![image](https://user-images.githubusercontent.com/79720695/129493495-e87dcc06-2f84-47f7-a875-c8427ee24a15.png)|![image](https://user-images.githubusercontent.com/79720695/129493500-bd75c099-b126-4e5d-ad42-05c5c2db8f51.png)|

The following Models were evaluated with parameter `n_estimators=100`

|Sampling Method|Balanced Accuray Score|Confusion Matrix|Imablanced Classification Report|
|---|---|---|---|
|Balanced Random Forest Classifier|77.5%|![image](https://user-images.githubusercontent.com/79720695/129494032-ce992a90-99af-461b-9e0e-ffc467301001.png)|![image](https://user-images.githubusercontent.com/79720695/129494030-78e04f46-78ce-470d-b28d-566d14e2b7cb.png)|
|EasyEnsemble w/ AdaBoost|92.5%|![image](https://user-images.githubusercontent.com/79720695/129494051-3b95e5d2-ca19-41e1-b8e1-1c5d33b82cc7.png)|![image](https://user-images.githubusercontent.com/79720695/129494054-6aa143ad-17e7-45c9-ba02-7829e756d670.png)|

### Feature Importances

Under the Balanced Random Forest Classifier, the highest impact features determined using `feature_importances_` were:
![image](https://user-images.githubusercontent.com/79720695/129494569-127caa7d-3b89-4bf5-928e-05a07ee055bc.png)


## Results Write-up
Undersamplnig method `Cluster Centroids` provided the least accurate model. While the EasyEnsemble w/ AdaBoost looks to be the most promising dataset with a Balanced Accuracy scoer of 92.5%, further evaluation should be undertaken to ensure the model is not overfit. Otherwise, the Balanced Accuracy score of 77.5% from the Balanced Random Forest Classifier presents itself as a very strong smapling method. 

Lastly, the top influential features used in the Balanced Random Forest Classifier are all 'retrosepctive' datapoints, in the sense that these datafields would not be useful  until after a significant time has past from the loan being issued. In this case, the model is more suited to flagging accounts that already are potentially at risk, rather than determining if a new loan will later become at-risk.

## Additional Information
- Data source:
  - LendingClub, a peer-to-peer lending services company.

