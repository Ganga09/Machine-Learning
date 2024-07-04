# ***Machine learning: Introduction***


We train machine using a dataset.

First thing we teach the machine is datasets
Heart data:Data for patients to know if the patient is diabetic or not, we can train the machine to identify if patient is diabetic or not.

two types of programming languages:
1) traditional programming
2) Machine learning


Machine learning is of 2 types:
Supervised ML algorithms: given data will contain input and corresponding output and a model is created based on that and the model will be capable to predict based on the trained data. each input have output
Unsupervised ML algorithms.

## **2 types of supervised ML : 1)Classification 2) Regression**

### ***1) Classification:***
input _output-> Classification model+> to predict categorical data
when we want the machine to predict a categorical data like yes/no, true/False 1/0 we use classification model, Eg predict is a person is diabetic or not, will rain or not etc.
Algorithms:

  **1)KNN**

  **2)Naive bayes** :
  
    * Gaussian: for continuos data
    * Multinomial: for discrete data and objects
    * Bernouli: combination of numerical and object data

  **3)Support vector machine**

  **4)decision tree**

  **5)random forest**



### ***2)Regression:***
input_output+> to predict a numerical data+>regression model.

Predict price of a used car.

Predict the rainfall to be received.

predict intrest rate based on credit score.
Examples:
1.   Simple Linear Regression
2.   Multiple linear Regression
3.   Polynomial Linaer Regression
4.   Decision Tree
5.   Random forest
4.   KNN








## Unsupervised Machine Learning:
input===> output

**Clustering**

Mainly used in market segmentation

## **Steps to be followed for ML model**


## 1)Data collection:
colletion for study purpose==>kaggle
## 2)Data Prearation and Exploration
###data cleaning==>
handle missing values, encoding,
Data visualization
### 3) Model creation
ML Algorithm
### 4)Performance evaluation
>70-75%
### 5) Improve performance


## ***Training and testing data***


Machine learn from training data, the performance is find from testing data.
Data set will be split into train and test data.(std : 70||30 percentage.)

dataset are split by random sampling so to keep the spliting constant we can you random state defined as 1, 0,42 etc

## ***Normalization:***

 ***Normalization:***
making all values to the same range.

###1) Standard scalar: z=(x-u)/s

 Where z is the output, x is the input sample u is mean of training data, s is standard deviation of training data.


***................normalization......................***

from sklearn.preprocessing import StandardScaler
1. *scaler=StandardScaler()*
2.  *scaler.fit(x_train) #covert xtrain value to normalized form.*
3.  *x_train=scaler.transform(x_train) #transform the x-train to norm value*
4.  *x_test=scaler.transform(x_test)*
5.  *print(x_train)*
6.  *x_tes*t



#### x_train is only fitted as the normalization works based on training data. It collects the mean and std deviation of training data







###2) Min-max scalar

## ***Performance Evaluation:***
............................................................................................

### ***Performance Evaluation:***


***###Classification model:***
*4 methods* All these work based on confusion matrics
1. Accuracy score: if >70% it is a good model:
  * from sklearn.metrics import accuracy_score
  * print("accuracy=:",score*100)

***Accuracy score:  TP+TN/TP+TN+FP+FN***
2. Recall : give importance to FN False negative. FN is when a positive or 1 is predicted as negative or 0
***Recall:  TP/TP+FN***

3. Precision:Focus on FP
***Precision:  TP/TP+FP***

4. F1_score:
***F1:  2x (recall+precision)/(recall+Precision)***

 When the given data is a balanced data then we can relay on accuracy score. If the data is imbalanced then we should not soley rely on accuracy score.
 when the target labes have a huge diffrence in number the data is called an imbalanced data.



###*Confusion matrics*
4 technical terms: **TP**:*true positive*, **TN**:*true negative*, **FP**:*false positive*, **FN**: *false negative*

1. **TP**:*true positive*: 1 predicted as 1 .....
2. **TN**:*true negative*: 0 predicted as 0

ie y_pred = y_test
3. **FP**:*false positive*: 0 predictd as 1: negative predicted as positive
4.  **FN**:*false negative*: 1 predicted as 0 : positive predicted as negative



* example:
y_test= 1 0 0 1 1 1 1 0 0 0 1 1 0 0 0 1       
y_pred= 1 1 1 0 0 1 0 1 1 1 1 1 0 0 1 1

Tp: 5. TN:2 FP:6 FN 3

## *Confusion matrics:*


1. from sklearn.metrics import confusion_matrix, accuracy_score
2. cm= confusion_matrix(y_test,y_pred)
3. print(cm)

from 2X2 confusion matrics its easy to identify the posiitive and negative but its hard for a 3x3 matrics so we'll need to plt them.

### *Plotting confusion matrics:*
1. from sklearn.metrics import ConfusionMatrixDisplay
2. labels=['Iris-versicolor', 'Iris-virginica', 'Iris-virginica'] # same order as y_train
3. cmd=ConfusionMatrixDisplay(cm,display_labels=labels) # give the variable  having confusion matrics in the bracket
4. cmd.plot()

## ***Encoding***


###1.Label encoding
Machine assigns numerical values to the labels.

Code:
*   from sklearn.preprocessing import LabelEncoder
*   lb=LabelEncoder()
*   name_encoder=lb.fit_transform(name)
*   name_encoder

disadvantage ; it automatically sets a hierarchy

###2. One_hot
the column is expanded to the number of unique categories.
One hot enoding: state column expands to New York', 'California', 'Florida

code:

* from sklearn.compose import make_column_transformer
* from sklearn.preprocessing import OneHotEncoder
* one= make_column_transformer((OneHotEncoder(handle_unknown='ignore'),['State']),remainder='passthrough')
* x=one.fit_transform(x)
###3. Get dummies


## Over fitting and under fitting




* > Errors in training data: bias
* > Errors in testing data: Varience

> *low bias and high varience:* ***Overfitting***

 * training data size is low or model is complex(use only required features)

>*high bias and low varience:* ***Underfitting***

* testing data errors low and traing data errors more

our model should neither be overfitted nor be underfitted

