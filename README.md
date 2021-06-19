# Loan-Prediction
Binary Classification model using a real-life case study of Dream Housing Finance to automate the loan eligibility process (whether the customer is granted a loan or not), based on customer details provided.

## Requirements
- Python = 3.7
- pandas = 0.20.3
- seaborn = 1.0.0
- sklearn = 0.19.1

## Dataset 
The dataset used for training and testing have been uploaded as 'train_ctrUa4K.csv' and 'test_lAUu6dG.csv' respectively. The test dataset does not have the target variable, 'Loan Amount', which is to be predicted. 

The dataset has the fields: _Loan_ID_ (C), _Gender_ (C), _Married_ (C), _Dependents_ (C), _Education_ (C), _Self_Employed_ (C), _ApplicantIncome_ (N), _CoapplicantIncome_ (N), _LoanAmount_ (N), _Loan_Amount_Term_ (N), _Credit_History_ (C), _Property_Area_ (C), and _Loan_Status_ (Target Variable).                                                                                  
###### (C) represents categorical variables while (N) represents  numerical variables.

## Data Visualization
### Univariate Analysis
After making a copy of the train and test dataset, we move on to variable analysis.

Each variable is examined individually. The seaborn library is used to plot graphs for analyzing both categorical and numerical variables.
This also allows us to identify variables with outliers.

### Bivariate Analysis
Variables (categorical and numerical) that might be correlated with the target variable (based on hypotheses) are plotted. A heatmap is plotted to visualize correlation between all the variables.

## Pre-Processing
- Missing values for numerical variables are filled using mean while mode is used for the categorical variables.

- Since the target variable has a significant number of outliers, we apply log transformation in order to get a distribution that is closer to normal. 

- Dummy variables are created for categorical variables (variables with values as 0 or 1)

## Model Building I

The train dataset is split into training (X) and testing (y) dataset. The model will be trained on X and tested for accuracy on y. If we get a good accuracy, we can apply the model on the test dataset

The LogisticRegression() function of the sci-kit library is used to train and test our model. 

We get an accuracy score of **79.4594%**. This means that the model can be used to predict the results of the test dataset  

## Model Building II 
We can also apply Logistic Regression using stratified k-folds cross validation. We make a model with 5 folds and make predictions on the test (y) dataset. 

The model gives us a mean accuracy of **80.1292%**
