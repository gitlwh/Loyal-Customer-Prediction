# Loyal-Customer-Prediction

This is code to generate my submission to the Kaggle competition - [Loyal Customer Prediction](https://inclass.kaggle.com/c/loyal-customer-prediction) as a final project of Lehigh CSE447. This submission managed to give me a 2nd place in the competition (under the alias [♕ Wenqi ♔](https://www.kaggle.com/weihengli)), in top 5%.

The challenge of this competition was to predict which shoppers that responded to a rebate coupon on a specific period, would become repeat buyers of that product. The given dataset was a nearly 1G dataset with one year history of transactions for each shopper.

The biggest difficulty in this competition was to create good features from the dataset of transactions as well as classification, which was then based on these features, and was a blend of various models:
* Extra Trees Classifier (scikit-learn)
* Gradient Boosting Classifier (scikit-learn)
* Gradient Boosting Classifier with Linear models as base estimators (xgboost)
* Quantile Regression (vowpal wabbit)

These models were then blended again using Gradient Boosting, trained on a holdout set of the training data.

## To recreate the submission

This submission requires an installation of xgboost, vowpal wabbit, pandas, numpy and scikit-learn, and has only been tested on MacOS. Note that since this is a large dataset, so I didn't upload dataset. You can download all data and put them in data folder.

* Download the competion data (*user_info.csv*, *user_log.csv*, *train_label.csv*, *test_label.csv*) and put it in the folder "data"
* Run *gen_features.py* to create the features files *train.csv* and *test.csv*
* Run *gen_result.py* to create the final submission
