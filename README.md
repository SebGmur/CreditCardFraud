# CreditCardFraud
Credit Card Fraud Detection (data from Kaggle Competition). Comparison of different techniques available in Scikit-learn.

This project is inspired by Kaggle competition “Credit Card Fraud Detection”. In this project, I have compared performance of “Logistic Regression”, “K-nearest neighbors”, “Support Vector Machine”, “Random Forest” and “XGBoost” models in detection of fraudulent credit card transactions.

This notebook contains data exploration and pre-processing using Pandas. Visualizations are performed using Seaborn. 
Dataset has been split into training (80%) and testing (20%) subsets randomly.
Dataset is highly imbalanced, there are 284315 (99.83%) of valid transactions and 492 (0.17%) fraudulent transactions. For these reason, data augmentation algorithms have been implemented: Under sampling of valid transactions, oversampling of fraudulent transactions and hybrid approach using SMOTETomek. 

RECALL is chosen as a best comparison metric because we want to make sure that we find as much fraudulent transactions (TRUE POSITIVE) as possible, and we will not expose credit card issuer to huge losses due to misclassifying fraudulent transactions as valid (FALSE NEGATIVE). Therefore, in this case we do not care too much if we misclassify valid transaction as fraudulent (FALSE POSTIVE), at least to certain number, because it will cost the card issuer some extra checks.

Support Vector Machine takes long time to learn therefore GridSearchCV as well as cross-validation has not been performed.



              Cross-Validation  RECALL Score
              | TEST SET | CV MEAN | CV MIN |
Logistic Reg. |    93%   |   62%   |  46%   |			  
    K-NN      |    100%  |   30%   |  25%   |
	SVM       |    69%	 |   --	   |   --   |  
Random Forest |    98%   |   76%   |   61%  |
XGBoost       |    100%  |   78%   |   61%  |

