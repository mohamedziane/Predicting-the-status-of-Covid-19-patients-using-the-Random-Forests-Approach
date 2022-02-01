
# Predicting the status of Covid-19 patients using the Random Forests Approach

<p align="center">
  <img width="600" height="400" src="https://media.springernature.com/lw630/nature-cms/uploads/collections/8k-covid19-scaled-29704a5e005f09a6edf1654fabcbdeb2-2ceb49ce47269d2527b2f6b7851cc52d.jpg">
</p>

## 1. Introduction: Coronavirus

Coronavirus disease (COVID-19) is an infectious disease caused by the SARS-CoV-2 virus.

Most people infected with the virus will experience mild to moderate respiratory illness and recover without requiring special treatment. However, some will become seriously ill and require medical attention. Older people and those with underlying medical conditions like cardiovascular disease, diabetes, chronic respiratory disease, or cancer are more likely to develop serious illness. Anyone can get sick with COVID-19 and become seriously ill or die at any age. 

The best way to prevent and slow down transmission is to be well informed about the disease and how the virus spreads. Protect yourself and others from infection by staying at least 1 metre apart from others, wearing a properly fitted mask, and washing your hands or using an alcohol-based rub frequently. Get vaccinated when it’s your turn and follow local guidance.

The virus can spread from an infected person’s mouth or nose in small liquid particles when they cough, sneeze, speak, sing or breathe. These particles range from larger respiratory droplets to smaller aerosols. It is important to practice respiratory etiquette, for example by coughing into a flexed elbow, and to stay home and self-isolate until you recover if you feel unwell.

Many governments recommended only essential outings to public places and closed most business that do not serve food or sell essential items. An excellent [spatial dashboard](https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6) built by Johns Hopkins shows the daily confirmed cases by country.

## 2. Objective

This case study was designed to drive home the important role that data science plays in real-world situations like this pandemic. This case study uses the Random Forest Classifier and a dataset from the South Korean cases of COVID-19 provided on [Kaggle](https://www.kaggle.com/kimjihoo/coronavirusdataset) to encourage research on this important topic. The goal of the case study is to build a Random Forest Classifier to predict the 'state' of the patient.

## 3. Dataset loading

- Importing packages
- Loading The Data
- Exploring the data

## 4. Cleaning, Transforming, and Visualizing

- Checking the intgerity of the data and fixing as much as possible.
- Handling Numerical Missing Data.
- Creating a new column named 'n_age' which is the calculated age based on the birth year column.
- Dropping Insignificant columns.
- Visualization
- Checking for duplicated rows.
- Handling Categorical Missing Data Using **KNN imputer "fancyimpute"** to encode and impute the missing Data.

<p align="center">
  <img width="400" height="400" src="https://camo.githubusercontent.com/9eeda4e6b3815387190937ca1afa724c650f1055ccc1a8a0b73a9eb5a3167e8d/68747470733a2f2f757365722d696d616765732e737472696b696e676c7963646e2e636f6d2f7265732f6872736379777634702f696d6167652f75706c6f61642f635f6c696d69742c666c5f6c6f7373792c685f313434302c775f3732302c665f6175746f2c715f6175746f2f3137343130382f3635343537395f3336343638302e706e67">
</p>

<p align="center">
  <img width="1000" height="500" src="https://raw.githubusercontent.com/mohamedziane/Predicting-the-status-of-Covid-19-patients-using-the-Random-Forests-Approach/main/images/img_correlation.png">
</p>

<p align="center">
  <img width="700" height="700" src="https://raw.githubusercontent.com/mohamedziane/Predicting-the-status-of-Covid-19-patients-using-the-Random-Forests-Approach/main/images/img_vizualization.png">
</p>

## 5. Random Forest Model

- Splitting the data into testing and training subsamples
- Scaling the data in prepartion of the model creation
- Fitting the Random Forest Classifier
- Classification Report
- Creating Confusion Matrix Plots

<p align="center">
  <img width="500" height="500" src="https://raw.githubusercontent.com/mohamedziane/Predicting-the-status-of-Covid-19-patients-using-the-Random-Forests-Approach/main/images/img_confusionmatrix.png">
</p>

## 7. Features Importance

<p align="center">
  <img width="500" height="400" src="https://raw.githubusercontent.com/mohamedziane/Predicting-the-status-of-Covid-19-patients-using-the-Random-Forests-Approach/main/images/img_featureimportance.png">
</p>

## 6. Hyperparameter Tuning using GridSearchCV

| <code>Random Forests (Base)</code> | <code>Random Forests (Tuned)</code>|
|:---------------------:|:---------------------:|
|Accuracy= 85.135 %|Accuracy= 86.712 %|
|f1_score= 82.546 %|f1_score= 83.112 %|

## 7. Conclusion

 * The Random Forests (Base) Model shows an overall <code>accuracy of 85%</code>, which is great and indicates that our model was effectively able to identify the status of the COVID-19 patients in the South Korean dataset despite the fact that we have an imbalanced class **"State"**, due to the nature of the dataset and the topic we're trying to tackle today which is Predicting COVID-19 Patients State , as shown below:

|<code>code</code>|<code>state</code>|<code>count</code>|
|:--:|:--: |:--:|
|1|isolated|    1878|
|2|released |    306|
|0|deceased |     34|

 * As shown above, after we fined tuned the Random Forest Parameters, we managed to improve the accuracy by 1.7% from 85% to 86.7% and there was a clear reduction in the Decision Trees size thus reducing memory consumption, the complexity and we find the split choices that will get us to the pure nodes much faster resulting in more information gain (more prediction power)

 * The popularity of random forest is primarily due to how well it performs in a multitude of data situations. It tends to handle highly correlated features well, where as a linear regression model would not. In this project we demonstrate the performance ability even with only a few features and almost all of them being highly correlated with each other. Random Forest is also used as an efficient way to investigate the importance of a set of features with a large data set. Consider random forest to be one of your first choices when building a decision tree, especially for multiclass classifications.

