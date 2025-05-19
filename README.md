# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the packages.

2.Analyse the data.

3.Use modelselection and Countvectorizer to preditct the values

4.Find the accuracy and display the result.

## Program:

```
Program to implement the SVM For Spam Mail Detection..
Developed by: KARTHICK S
RegisterNumber:  212224230114
```

```
import pandas as pd
data = pd.read_csv("/content/spam (1).csv",encoding='windows-1252')
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/d2530e45-04c9-4a2f-8993-20538ef38df9)

```
data.info()
```
## Output:
![image](https://github.com/user-attachments/assets/a6bae8a4-b611-429e-912b-809bf600888e)

```
print(data)
```
## Output:
![image](https://github.com/user-attachments/assets/8e3b35c1-68aa-437b-ac2c-30b5fb1aa4c1)

```
x = data['v2'].values
y = data['v1'].values
```
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=11)
```
## code:
![image](https://github.com/user-attachments/assets/ab614d02-c0bb-4452-a9b0-c3a26a280957)

```
from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer()

x_train = cv.fit_transform(x_train) #converts text to numerical daya with an adjustable size
x_test = cv.transform(x_test)

type(x_train)
```
## Output:

![image](https://github.com/user-attachments/assets/f2d57134-5c30-4d94-a541-08966bc0ce59)
```
x_train
```
## Output:
![image](https://github.com/user-attachments/assets/4dcdc8e3-f419-421e-b468-20e2abaf71df)

```
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
```
## Output:
![image](https://github.com/user-attachments/assets/91d0a984-f0e2-400a-9790-fdc2f78e9a57)

```
from sklearn.metrics import accuracy_score
accuracy_score(y_test,y_pred)
```
## Output:
![image](https://github.com/user-attachments/assets/b9362ffa-633c-423e-af31-18aa0a3ee982)


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
