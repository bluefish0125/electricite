# electricite

### Challenge Goals
The aim is to model the electricity price from weather, energy (commodities) and commercial data for two European countries - France and Germany. The problem here is to explain the electricity price with simultaneous variables and thus this is not a prediction problem. More precisely, the goal of this challenge is to learn a model that outputs from these explanatory variables a good estimation for the daily price variation of electricity futures) contracts, in France and Germany. The metrics of evaluating performance is the spearman correlation coefficient.

### My Approach
I reduced the skew in the data with transformations, centered & scaled the data, and performed PCA on the dataset to capture 95% of variance. Then I used Optuna to perform hyperparameter tuning on my neural network and found parameters that gave me a spearman correlation of 0.317. The problem that I encountered is that I am not sure how to improve my spearman correlation as 0.317 is still relatively weak. Any tips on improving my preprocessing and hyperparameter tuning phases would be greatly appreciated. Another issue I have is that Model Testing and Second Testing have significantly different results for reasons I cannot pinpoint. The only thing I had changed was the random_state and the manual seed. Appreciate any feedback!

