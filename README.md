## Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee
## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:

1.Hardware – PCs
2.Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import pandas to read the csv files.
2.Display the head and tail of the dataset.
3.Import LabelEncoder() from sklearn.preprocessing.
4.Label the data which are not in the integer type.
5.Assign the X and Y from the dataset.
6.Split the dataset using train_test_split from sklearn.model_selection.
7.nImport DecisionTreeRegressor from sklearn.tree
8.Fit the Training set in a variable.
9.Import metrics from sklearn to find the Mean Squared Error.
10.Predict the result for the given values.
```
## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: SOUVIK KUNDU
RegisterNumber: 212221230105
*/
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x = data[["Position","Level"]]
x.head()
y = data["Salary"]
y.head()
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2=metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```
## Output:
1. data.head():
   ![1s](https://github.com/souvik798/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94752764/14cff4a7-9f35-45ff-81e6-e7b2d1026a4e)

   
2. data.info():
   ![2s](https://github.com/souvik798/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94752764/56b1c51e-e554-4812-8df9-50d7d1a4b772)


3.isnull()and sum():
    ![3s](https://github.com/souvik798/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94752764/ff649bf1-2c3c-41c7-89c2-1bc5eaf574d5)


4.data.head() for salary:
    ![4s](https://github.com/souvik798/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94752764/ef9d346d-cb64-486e-931b-bb07bfb0c76b)


5. MSE value:
    ![5s](https://github.com/souvik798/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94752764/21d10ef4-c657-48e8-8505-e9b0a8ca471b)


6. r2 value:
    ![6s](https://github.com/souvik798/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94752764/2057274d-376e-450d-b2f9-0dc4acb0457a)


7. data prediction:
     ![7s](https://github.com/souvik798/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/94752764/f0c80755-62d7-473e-89c0-4de767ad1f0c)


## Result:

   Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
