# Clustering
readme.md

Cluster Analysis

The goal is to perform cluster analysis on the Adult dataset. Finally, evaluation measures, experimental setup and parameter selection has been discussed and the conclusions are justified.

Dataset used:

Dataset name: Adult dataset
Task: Classification
Prediction: To determine whether a person makes over 50K a year.
Labels: >50K,<=50K
Dataset characteristics: Multivariate
Attribute characteristics: Categorical, Integer
Number of Instances(Total): 48842
Number of Instances(Train):32561
Number of Instances(Test):16281
Number of Attributes:14

Platform : Google colab
Package: Usage for pip install

pip install -U scikit-learn

or conda:

conda install scikit-learn

Prediction task is to determine whether a person makes over 50K a year.

Data Preprocessing and Transformation:

Data integration
Data cleaning
Data reduction

Feature Selection:
Used PCA and MCA methods for feature selection.Chi square test for categorical variables has been performed.

Clustering :
Kmeans Clustering 
DBSCAN Clustering

Factor Analysis with Mixed Data type (FAMD) would be useful to integrate the types of features so that we have used it for clustering

famd = FAMD(n_components = 130, random_state = 101).fit(X_train)
famdX = famd.transform(X_train)

fit an estimator(classifier) to be able to predict the cluster to which unseen samples belong 
 
classifier.fit_predict(famdX)

Plot the evaluation results using matplotlib.


Results from the two clustering models:

   Clustering method         Silhouette Score       Calinski Harabasz Score        Homogeneity                 V measure 
| -- ----------------        -----------------      -----------------------    --------------------      -------------------------
| 1  Kmeans                   0.033033842387030325     518.2063318951402       0.12071297068287776          0.09516286207604767     
| 2  DBSCAN                   0.2019493802324271      183.24277459524927     2.299297083879762e-05          2.7832754085483524e-05


Results from Measures of Fairness - Statistical Parity Difference (SPD)

Clustering method                       spd_00                                                 spd_011              
| -- ----------------     -------------------------------------     --------------------------------------------------------------   
| 1  Kmeans               0: -0.03178, 1: 0.34589, 2: 0.02787     0: 0.34528, 1: 0.02418, 2: 0.00360, 3: -0.03144, 4: 0.00034
| 2  DBSCAN               0: 0.30754, 1: 0.00172, -1: 0.03270     0: 0.30244, 1: 0.00287, 2: 0.00203, -1: 0.03462















