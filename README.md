# Predicting Property Maintanance Fines

Blight violations are issued by Detroit to individuals who allow their properties to remain in a deteriorated condition. Every year, the city issues millions of dollars in fines to residents and every year, many of these fines remain unpaid. Enforcing unpaid blight fines is a costly and tedious process, so the city would like to know how to increase blight ticket compliance. The task of this analysis is to predict whether a given blight ticket will be paid on time.

Two data files retrieved from the Detroit Open Data Portal are used for training and validating the models. Each row in the two files corresponds to a single blight ticket, and includes information about when, why, and to whom each ticket was issued. The target variable is compliance, which is True if the ticket was paid early, on time, or within one month of the hearing data, False if the ticket was paid after the hearing date or not at all, and Null if the violator was found not responsible. 

### File descriptions
train.csv - the training set (all tickets issued 2004-2011)

test.csv - the test set (all tickets issued 2012-2016)

addresses.csv & latlons.csv - mapping from ticket id to addresses, and from addresses to lat/lon coordinates. 

### Data Fields
Includes ticket id, agency name, inspector and violator name, addresses, violatoin and hearing dates, disposition, fine and total judement amounts, late fees.

Compliance: 0 = non-compliant (did not pay the fine), 1 = compliant (paid the fine)

### Evaluation
A number of models were tested to choose which model would produce the highest accuracy. The models include logistic regression, random forests, gradient boosted decision trees, K-nearest neighbors, Naïve Bayes and support vector machines. Model parameters were optimized for each model to produce most accurate results.  The predictions are given as the probability that the corresponding blight ticket will be paid on time. The evaluation metric is the Area Under the ROC Curve (AUC).

### Results

The gradient boosted decision trees produced the best results with an AUC of 0.78:

