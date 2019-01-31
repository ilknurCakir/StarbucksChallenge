# StarbucksChallenge


#### Table of Contents

1. [Installation](#Installation)
2. [Project Motivation](#ProjectMotivation)
3. [File Descriptions](#FileDescription)
4. [Results](#Results)
5. [Licensing, Authors and Acknowledgements](#Licensing)

###  Installation
<a name="installation"></a>

Libraries used: pandas, numpy, sklearn, imbalanced-learn, matplotlib, seaborn

### Project Motivation
<a name="ProjectMotivation"></a>

Data includes features, response variable showing if the customer purchases the
product and a dummy variable showing if a promotion code is sent out to the
customer. No further details about the features. Training data is split into
two groups; control and treatment. Promotion is sent to only customers in the
treatment group to see if it increases revenue.

Only 0.7% of customers buy the product in control group and this figure is 
around 1.7% in treatment group. In other words, data is heavily imbalanced.

The product is $10 and sending a promotion incurs unit cost of $.15.

The task here is to develop a strategy to find to whom Starbucks should send
promotions out so that it maximizes net incremental revenue(NIR) and 
incremental response rate (IRR). They are defined as follows:

NIR = 10 * (purchase in treatment) - 0.15 * promotions 
				+ 10 * (purchase in control)

IRR = (purchase in treatment / allcustomers in treatment) - 
		(purchase in control / all customers in control)

### File Description
<a name="FileDescription"></a>

Files in the folder;

training.csv - training data
starbucks.ipynb - includes data exploration, includes strategy developed and 
					testing the strategy

.png files - visualizaions

### Results
<a name="Results"></a>

1. Machine learning models cannot perform well even with tuned hyperparameters

2. Models trained with oversampled data are prone to overfit. The results in 
downsampling are better than they are in SMOTE.

3. ROC AUC score is plotted with differing threshold values in classification.
The optimal value is between 0.49-0.5. For the rest of the work, 0.5 is used.

4. Extreme Gradient Boosting gives the best results as 73.3% recall, 
3% precision and 0.66 ROC AUC score.

5. Testing the strategy gives that 1.96% more customers buy the product and
net incremental revenue of $398.4.

### Licensing, Authors and Acknowledgements
<a name="Licensing"></a>

MIT License
