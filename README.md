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

![image](https://github.com/user-attachments/assets/ba1dc705-9750-46f2-833a-1c28ec3e1d50)
```
df=sns.load_dataset('tips')
df
```

![image](https://github.com/user-attachments/assets/d37f6af3-1667-451e-a52f-81d92d73c454)
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```

![image](https://github.com/user-attachments/assets/cb0d2704-3557-4255-82f9-7fade12ded85)
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

![image](https://github.com/user-attachments/assets/a4a1d138-902f-487f-8d1d-d0d45bc8a27d)
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

![image](https://github.com/user-attachments/assets/7e835930-8b14-49e8-9589-6de464f19ef8)
```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bilal', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```


![image](https://github.com/user-attachments/assets/151ab83b-539e-484a-a524-fb7c858adf05)
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
```
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```

![image](https://github.com/user-attachments/assets/71198831-3f84-4310-befc-e38802e33fbc)
```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```

![image](https://github.com/user-attachments/assets/be6612ce-b177-4064-9769-92a11ba1ec11)
```
from google.colab import drive
drive.mount('/content/drive')
```
```
ls drive/MyDrive/DS2024/titanic_dataset.csv
```
tit=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
tit
```

![image](https://github.com/user-attachments/assets/f6c63442-1157-4192-9466-7a0287cf92d8)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```

![image](https://github.com/user-attachments/assets/66f6fab4-a7a9-485b-ba7e-463bcd8ced01)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```

![image](https://github.com/user-attachments/assets/0ac9567b-84a5-467f-9627-87aac837bb7e)
```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![image](https://github.com/user-attachments/assets/7bebdfb4-372c-4113-92a1-c2acac0f4eab)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```

![image](https://github.com/user-attachments/assets/8d0e2d67-df54-4fed-9404-30fa0b29a8fb)

```
sns.histplot(data = num_var, kde = True)
```

![image](https://github.com/user-attachments/assets/74a1e537-f6ab-4b7b-b900-b8d976e4fd8d)
```
df=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```

![image](https://github.com/user-attachments/assets/f6ab257c-87ab-469a-9363-6906d11c1bdf)
```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```

![image](https://github.com/user-attachments/assets/bd6f5aa3-a7f2-4831-bf26-904c0541cefa)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```

![image](https://github.com/user-attachments/assets/6d84307d-b2a2-4996-8e64-c332ad6754ff)
```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```

![image](https://github.com/user-attachments/assets/5c9fa8bd-2442-4621-99a7-f788fd408fe3)
```
mart=pd.read_csv("drive/MyDrive/DS2024/titanic_dataset.csv")
mart
```

![image](https://github.com/user-attachments/assets/f390a9ae-b064-4ce1-bbad-5251a5510db8)
```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```

![image](https://github.com/user-attachments/assets/45be149e-26ea-4dd8-a0f5-9dd82491cf62)
```
sns.kdeplot(data=mart,x='PassengerId')
```

![image](https://github.com/user-attachments/assets/6b34f0cb-6282-4d5a-832e-ed83c851d279)
```
sns.kdeplot(data=mart,x='Age')
```

![image](https://github.com/user-attachments/assets/c261cfee-f93b-4070-835a-803d86cb4039)
```
sns.kdeplot(data=mart)
```

![image](https://github.com/user-attachments/assets/281db2d5-4325-4b36-8fdb-daa244e2949e)
```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```

![image](https://github.com/user-attachments/assets/d7b3c8c8-2779-4266-b3fe-28cb77ad57ba)
```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```

![image](https://github.com/user-attachments/assets/e4045a80-6274-499d-b584-7fce682a7883)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```

![image](https://github.com/user-attachments/assets/5c56f798-8ff3-44a6-a800-f579c349c880)

```
hm=sns.heatmap(data=data)
```

![image](https://github.com/user-attachments/assets/71aa265b-965b-4eae-9f89-566e717fa4f6)


 Include the necessary coding and corresponding screenshots

# Result:
Thus, all the data visualization techniques of seaborn has been implemented.

