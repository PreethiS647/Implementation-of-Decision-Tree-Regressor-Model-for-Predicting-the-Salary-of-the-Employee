# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

Load and Preprocess Data
Split the Data into Training and Testing Sets
Train the Decision Tree Regressor Model
Make Predictions and Evaluate the Model
## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Preethi S
RegisterNumber:  212223230157
*/
```
```
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()
```
![image](https://github.com/user-attachments/assets/849077c7-902c-4a55-b96f-997009832524)

```
data.info()
```
![image](https://github.com/user-attachments/assets/945bb676-0cee-4fbc-a6db-c531a3475fe6)
```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/9f583114-b9dd-4fc0-a52c-6f6c7b29f654)
```
data["Salary"].value_counts()
```
![image](https://github.com/user-attachments/assets/87225a26-bd3f-4096-92de-2ae43b01269a)

```
from sklearn.preprocessing import LabelEncoder 
le = LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
![image](https://github.com/user-attachments/assets/7e042c0b-1b69-431e-93f4-f22f73d3ebba)
```
x = data[["Position", "Level"]]
y = data[["Salary"]]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train, y_train)
```
![image](https://github.com/user-attachments/assets/eb01b780-7741-4277-b31a-c6ab8e922565)

```
y_pred = dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test, y_pred)
r2 = metrics.r2_score(y_test, y_pred)
mse
```
![image](https://github.com/user-attachments/assets/465d195c-ae13-4145-b086-48d6bcb9f61b)
```
r2
```
![image](https://github.com/user-attachments/assets/370dac86-f79a-446b-bd74-0429783b0000)
```
dt.predict([[5,6]])
```
![image](https://github.com/user-attachments/assets/41620331-1b4a-4943-9847-6e5c6a1c56d8)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
