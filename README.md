# electricite

### Challenge Goals
The aim is to model the electricity price from weather, energy (commodities) and commercial data for two European countries - France and Germany. The problem here is to explain the electricity price with simultaneous variables and thus this is not a prediction problem. More precisely, the goal of this challenge is to learn a model that outputs from these explanatory variables a good estimation for the daily price variation of electricity futures contracts, in France and Germany. The metrics of evaluating performance is the spearman correlation coefficient. Spearman's correlation coefficient measures the strength and direction of association between two ranked variables. The challenge link is: https://challengedata.ens.fr/challenges/97

The benchark for this challenge consists in a simple linear regression, after a light cleaning of the data: The missing (NaN) values are simply filled with 0's and the COUNTRY column is dropped - namely we use the same model for France and Germany. The public score obtained with this benchmark is 15.86%.

### My Approach
In the initial preprocessing phase, I prepared the dataset for Principal Component Analysis (PCA) by employing skewness-reducing transformations and ensuring uniformity through centering and scaling procedures. Subsequently, I conducted a series of experiments utilizing Lasso regression for effective feature selection and PCA for dimensionality reduction. These steps aimed to distill the most relevant information from the dataset. PCA does this by identifiying patterns in a data set, and then reducing the dataset to their most important features so that the data is simplified without losing important traits. In pursuit of optimizing model performance, I leveraged Optuna for hyperparameter tuning on neural networks and random forest regression.

### My Result
After an extensive search in the hyperparameter space and different preprocessing procedures, the resulting configuration yielded a Spearman correlation coefficient of 35.41%, indicating a moderate positive monotonic relationship between the predicted and actual values. In the specific context of daily volatility of dynamic european electricity futures, a spearman correlation of 35.41% holds significant value. Through experimentation, it was revealed that optimal performance was achieved when employing PCA exclusively and not incorporating Lasso regularization. The Lasso regularization removed an excessive number of features, and it turned out that a considerable portion of these features held predictive value. Optimal results were obtained by utilizing neural networks instead of random forest regression. 
