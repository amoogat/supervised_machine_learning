# Supervised Machine Learning
This project splits data into test and train data in order to assess success rates of supervised machine learning algorithms. These algorithms include random oversampling, SMOTE oversampling, undersampling and SMOTEENN (over and undersampling) to gauge the varying ability for their prediction success. The algorithms all use multiple factor linear regression on the data set columns (eg. loan amount and loan type) to get an approximate fit for loan success; it then tests this model on the test data to gauge effectiveness.

## Results
As can be seen in the challenge.ipynb classification reports (4 total: 1 for each model), the f1 score is highest in the **oversampling approaches**. The f1 score is a measure of a test's accuracy, taking the harmonic mean of precision and recall. [source](https://deepai.org/machine-learning-glossary-and-terms/f-score) 

We can see that in the SMOTE oversampling approach, the recall (rec) remains relatively high for both high_risk and low_risk. This would indicate a rather successful model, though the precision of the high_risk is woefully low at 1%. This indicates uncertainty in the ability to predict a high risk for a loan which is, after all, what this model is intended to do.

Therfore, **given the low amount of high_risk applicant data provided**, the best approach is the one that directly oversamples the high risk data to correct this sample imbalance. On average, it will correctly predict the risk level of an application 80% of the time. However this is nothing to get too excited about, as in reality, only around 347/68470 or ~0.5% of applications are ever high risk, and one could technically be ~99% correct by assuming each one is low risk. (see: [precision recall tradeoff](https://www.machinelearningaptitude.com/topics/machine-learning/what-is-precision-recall-tradeoff/#:~:text=Precision%20is%20the%20fraction%20of,total%20positives%20in%20the%20dataset))
