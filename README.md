# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/b576db6a-697a-4025-bc86-2e3874b86ca3)
```
df=sns.load_dataset('tips')
df
```
![image](https://github.com/user-attachments/assets/18d04be1-1abc-470a-959a-9d2c4f87b0e3)
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![image](https://github.com/user-attachments/assets/39f27047-d44c-4731-83a4-90fe84cbcd7e)
```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")

```
![image](https://github.com/user-attachments/assets/2c27d832-d506-4452-9934-7290e7b4457c)
```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```

![image](https://github.com/user-attachments/assets/53893bbe-2a9b-4072-9b7a-f66926e59755)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bilal', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```

![image](https://github.com/user-attachments/assets/222145af-0595-4f84-a624-9dc345372159)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
```
```
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```

![image](https://github.com/user-attachments/assets/2e751e55-16e0-479a-a8a1-cb685a9e800e)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```

![image](https://github.com/user-attachments/assets/6489c637-45ca-459e-8920-8a5630bb5eeb)

```
from google.colab import drive
drive.mount('/content/drive')
```
```
ls drive/MyDrive/DS2024/titanic_dataset.csv
```
```
tit=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
tit
```

![image](https://github.com/user-attachments/assets/59503ce6-cc83-4060-8311-9822866c28d5)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```

![image](https://github.com/user-attachments/assets/2daa5810-0a44-4fb2-9cf7-211e34b48c53)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```

![image](https://github.com/user-attachments/assets/39469f89-ae2b-4c82-bc50-4c8a48bb06a7)
```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![image](https://github.com/user-attachments/assets/6b603a0f-365b-47c9-ae8b-c0ac302a35b5)
```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```

![image](https://github.com/user-attachments/assets/8b1c4517-1c02-4d71-acb8-3ef83715c497)
```
sns.histplot(data = num_var, kde = True)
```

![image](https://github.com/user-attachments/assets/30605715-48e8-4862-8fd8-b538284e7527)

```
df=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```

![image](https://github.com/user-attachments/assets/57629e2b-a520-4b7f-9648-c84fa81cabd2)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```

![image](https://github.com/user-attachments/assets/d9c513e8-0139-438c-9bbb-74a31fa6021f)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```

![image](https://github.com/user-attachments/assets/cb2bb2ee-081b-4c5a-a983-6a47547831cd)
```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```

![image](https://github.com/user-attachments/assets/d86a1273-a881-496b-bd23-fcfeaa1aeb4d)
```
mart=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
mart

``
![image](https://github.com/user-attachments/assets/c42482ae-4cab-4da2-ac63-84f447af09ec)
```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```

![image](https://github.com/user-attachments/assets/74a20c77-a3c6-4ba5-a334-458953476935)
```
sns.kdeplot(data=mart,x='PassengerId')
```

![image](https://github.com/user-attachments/assets/8a36ebb0-8371-463d-8431-0c81ff09df99)
```
sns.kdeplot(data=mart,x='Age')
```

![image](https://github.com/user-attachments/assets/5fe929e2-b755-4250-bb6f-a4be61afbd10)
```
sns.kdeplot(data=mart)
```

![image](https://github.com/user-attachments/assets/424c3f9c-5091-4cfb-acc9-fba9867f1e5e)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```

![image](https://github.com/user-attachments/assets/d0d1edce-7ea7-48e7-9f11-e8420e0bc01a)
```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```

![image](https://github.com/user-attachments/assets/6467620b-0cdc-4092-aafc-bd0e0ecc8f09)
```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```

![image](https://github.com/user-attachments/assets/d1ad9044-b136-4580-8eeb-88934cca2c66)

```
hm=sns.heatmap(data=data)
```

![image](https://github.com/user-attachments/assets/dd06ee29-0697-40f9-9164-8ad8f8b56886)









 Include the necessary coding and corresponding screenshots

# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
