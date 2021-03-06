# Insurance Classification Problem

### Pujan Malavia 

![insurance](https://user-images.githubusercontent.com/19572673/85812626-262c3a00-b72f-11ea-8972-5af41645668e.jpg)

### Abstract:

Being able to build a model only through new feature creation, only with internal data provided, and being able to do model tuning with appropriate parameters to build out the best model possible to classify a binary outcome (1 or 0) through mostly numeric variables

Rules:

New features can be created.

Users cannot add or supplement with external data. 

While simple techniques may develop adequate models, success in this exercise typically involves feature engineering and model tuning.
Throughout your code, please use comments to document your thought process as you move through exploratory data analysis, feature engineering, model tuning, etc.  

### Industry: 
Insurance

### Company Infomration:
Undisclosed (InsuranceX)

### Use Case:
Insurance Classification Task based on mostly numeric variables

### Tool: 
R

### Techniques: 

Random Forest

AdaBoost

### Data Fields:
x0 - x99

### Data Curation Process:

The two classification algorithms I used were Random Forest and AdaBoost. The Random Forest is a bagging technique where a certain number of decision trees are grown on different subsets of the training data. It is also known to have low bias and high variance and has an equal amount of say in the final decision in modeling. AdaBoost is a boosting technique that uses stumps instead which would be a decision tree with only one split. These stumps, also known as weak learners, have high bias and low variance). The AdaBoost also has a different amount of say in the final decision. 

In the first trial, I performed the following data preparation/data cleansing techniques for both the train/test and validation set.  
1. Checking missing values
2. Doing mean imputation since roughly less than a fraction of a percent of data was missing
3. Standardizing/normalizing data based on a scale from 0 to 1.
4. Performed PCA (feature extraction) to see which variables show most variance among dataset
5. Identified the top ten predictors based on PCA plot to test out on model.
6. Visualized data via a histogram, boxplot, PCA plot, heat map(s), and a Scree plot.

### Data Visualization (1st Trial)

R

Scree Plot

![Scree_plot](https://user-images.githubusercontent.com/19572673/81483575-3a62b900-920d-11ea-873b-d8d05c6233b5.png)

PCA

![PCA](https://user-images.githubusercontent.com/19572673/81483573-3a62b900-920d-11ea-9a52-509c7d4bb1f7.png)

PCA 2

![PCA_2](https://user-images.githubusercontent.com/19572673/81483574-3a62b900-920d-11ea-8d19-9feef8fa78da.png)

Comp Features Heat Map

![Comp_Features_Heat_Map](https://user-images.githubusercontent.com/19572673/81483571-39ca2280-920d-11ea-983e-10d193c31e9d.png)

Features Correlation Heat Map

![Features_Correlation_Heat_Map](https://user-images.githubusercontent.com/19572673/81483572-3a62b900-920d-11ea-80f4-47fd4f9bbc73.png)

Histogram Predictors

![Histogram_Predictors](https://user-images.githubusercontent.com/19572673/81484631-10ad9000-9215-11ea-88cb-6ffe0ebe611a.PNG)

PC Barplots

![PC-barplots](https://user-images.githubusercontent.com/19572673/82132779-6bb12b00-97b1-11ea-8800-2f8590662e72.PNG)

The Random Forest performed with an 82.75% accuracy on the training set and an 81.43% accuracy on the test set. The AdaBoost performed with an 80.6% accuracy on the training set and an 80.7% accuracy the test set. 

In the second trial, I performed the following data preparation/cleansing techniques for both the train/test and validation set.  
1. Treated outliers by winsorizing and capping certain variables
2. Bucketed/binning/categorized numerical data
3. Performed interactions between predictors to see new patterns
4. Tuned the model to help improve the overall model accuracy

With Outliers

![BP_Outliers1](https://user-images.githubusercontent.com/19572673/81614459-11c5f500-93ae-11ea-9dd6-7ef3dd3617aa.png)

Outliers Removed

![BP_Outliers_Gone_1](https://user-images.githubusercontent.com/19572673/81614456-112d5e80-93ae-11ea-8acb-a2f683daa7a4.png)

However, in the second trial, the accuracy level did improve. The Random Forest performed with an 91.31% accuracy on the training set and with an 91.36% accuracy on the test set. The AdaBoost performed with an 93.2% accuracy on the training set and with an 96.8% accuracy on the test set. Thus, the highest model accuracy I received was from AdaBoost.

I believe that the AdaBoost would perform the best with what the data I was given. I believe that the choices I made in the context of the exercise would be different in a business context. For example, this dataset only included numerical variables as maybe in a business context, there would categorical variables that could be ordinal in nature (which allows transformation of those variables) to see their impact on the model. Sometimes, real-world data seems to be much more messier in nature where they could have a higher percentage of missing values in the dataset as well as more outliers that could skew the model (obviously depending on the methods used to treat them). In addition, while working a real-world setting, you would know some variables that historically tend to predict well (from a business context), and which ones do not. 

### Communication of Results to Business Partner:

To a business partner, I would explain that the Random Forest (all else equal) would work better for complex data (high variance, low bias) that’s a bit more unknown in terms of predictors’ effect on the response variable since it looks at all predictor variables equally in terms of its importance. However, for AdaBoost, although it has a higher accuracy rate, is better for ‘biased’ data vs. data with a lot of variance. However, the caveat is that sometimes the results of AdaBoost has a higher probability of seeing new data and predicting ‘wrong’ if that new set of data has more variance.

### Future Work:

Continue to do hyperparameter tuning of the model and creating new features/removing old features to help increase the prediction accuracy of the model

Try other types of models to see if the accuracy rate improves

More data visualization/patterns within the dataset (external sources) that can lead to more insights and decision-making from a business perspective
