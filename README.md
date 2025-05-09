# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.import pandas module and import the required data set.
2.Find the null values and count them.
3.Count number of left values.
4.From sklearn import LabelEncoder to convert string values to numerical values.
5.From sklearn.model_selection import train_test_split.
6.Assign the train dataset and test dataset.
7.From sklearn.tree import DecisionTreeClassifier.
8.Use criteria as entropy.
9.From sklearn import metrics.
10.Find the accuracy of our model and predict the require values.
## Program && Output:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: VAMSI KRISHNA G
RegisterNumber: 212223220120 
*/
```
~~~
import pandas as pd
data = pd.read_csv(r"C:\Users\admin\Downloads\Employee.csv")
data.head(5)
~~~
![image](https://github.com/user-attachments/assets/f4771960-9619-450b-bef3-88811974605b)
~~~
data.isnull().sum()
~~~
![image](https://github.com/user-attachments/assets/dbac44b4-56b4-4d12-aa3a-fef6fb5602e9)
~~~
data["left"].value_counts()
~~~
![image](https://github.com/user-attachments/assets/20c2bb89-c48c-4fba-a7d2-5a94cf3b1ab1)
~~~
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
~~~
![image](https://github.com/user-attachments/assets/6bb95f6d-f54b-4bb6-aaa7-48f3165c3513)
~~~
x=data[["satisfaction_level","last_evaluation","Work_accident","promotion_last_5years","number_project","average_montly_hours","time_spend_company","salary"]]
x.head()
~~~
![image](https://github.com/user-attachments/assets/92af734c-0bed-4ee7-b6c2-773508e451c6)
~~~
y=data['left']
y.head()
~~~
![image](https://github.com/user-attachments/assets/f1e864bc-a4a9-4092-99b9-3345e262ab35)
~~~
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)

from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred
~~~
![image](https://github.com/user-attachments/assets/db82a427-53ac-4588-820f-e4975d5b098a)
~~~
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
~~~
![image](https://github.com/user-attachments/assets/1266b8f9-1a3c-4559-8038-3f72e69fe952)
~~~
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
~~~
![image](https://github.com/user-attachments/assets/88d41067-0700-4ae9-8d38-5658528d0eb2)
## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
