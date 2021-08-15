# Credit_Risk_Analysis

## Project Overview
A credit card risk evaluation program will be created using machine learning with `imbalanced-learn` and `scikit-learn` libraries.

Approach: results from oversampling the dataset will be demonstrated with `RandomOverSampler` and `SMOTE` algorithims, results from undersampling will be demonstrated using the `ClusterCentroids` algorithm, and a cmoinatrotial approach of over- and undersampling will be demonstrated using the `SMOTEEN` algorithm. Lastly, `BalancedRandomForestClassifier` and `EasyEnsembleClassifiers` will be used as the final predictive models.


## Analysis/Machine Learning Results
|Method|Balanced Accuray Score|Confusion Matrix|Imablanced Classification Report|
|---|---|---|---|
|Random Oversampling|65.6%|![image](https://user-images.githubusercontent.com/79720695/129493402-a0e45ecc-1dea-4769-9365-57793795817b.png)|![image](https://user-images.githubusercontent.com/79720695/129493407-7e7984ed-29cb-4346-b05b-4d3122c12d74.png)|
|SMOTE Oversampling|63.6%|![image](https://user-images.githubusercontent.com/79720695/129493419-1420ac56-b348-41f8-9f4c-7b5ee69b58c2.png)|![image](https://user-images.githubusercontent.com/79720695/129493429-f61e2d26-ca0d-4cd7-8ac2-ba9f3b6ab8a2.png)|
|Central Centroid (Undersampling)|52.3%|![image](https://user-images.githubusercontent.com/79720695/129493441-0d0da9cb-3a9f-4acc-ba7a-b0f5b270bd05.png)|![image](https://user-images.githubusercontent.com/79720695/129493445-9c249137-3abe-4db8-a327-17a7543dc385.png)|
|SMOTEENN (Combinatorial)|63.1%|![image](https://user-images.githubusercontent.com/79720695/129493495-e87dcc06-2f84-47f7-a875-c8427ee24a15.png)|![image](https://user-images.githubusercontent.com/79720695/129493500-bd75c099-b126-4e5d-ad42-05c5c2db8f51.png)|


## Additional Information
- Data source:
  - LendingClub, a peer-to-peer lending services company.

