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
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
# Output
![image](https://github.com/user-attachments/assets/50804ff0-1e8c-431f-9d9b-b8bf37c38ec6)

```
df = sns.load_dataset("tips")
df
```
# Output
![image](https://github.com/user-attachments/assets/dea59582-1bf9-4fbc-89b2-008b3732ea3d)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
# Output
![image](https://github.com/user-attachments/assets/d1d81493-7af4-4089-abd5-38562a6378b5)

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
# Output
![image](https://github.com/user-attachments/assets/0c91352d-ae89-4125-a485-4a3055ae632f)

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
# Output
![image](https://github.com/user-attachments/assets/e1ef0630-9742-4a70-9431-f33104a1b7ab)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
# Output
![image](https://github.com/user-attachments/assets/e83f12bf-e7ca-472d-86dd-89445afbb0a5)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939] 
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
# Output
![image](https://github.com/user-attachments/assets/229c040c-c610-45b6-9742-08b4fe66a6ad)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
# Output
![image](https://github.com/user-attachments/assets/987f3eba-972e-4057-bbc7-5a9357046072)

```
ti=pd.read_csv("/content/titanic_dataset (2).csv")
ti
```
# Output
![image](https://github.com/user-attachments/assets/571c4630-a2c5-4a82-bcc8-5a2e616d8b68)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=ti, palette='rainbow') 
plt.title("Fare of Passenger by Embarked Town")
```
# Output
![image](https://github.com/user-attachments/assets/1b48b6de-a76a-4d2e-a46b-d42f268cb232)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=ti, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
# Output
![image](https://github.com/user-attachments/assets/e89e2baa-2798-4510-9fe4-e5d206394241)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
# Output
![image](https://github.com/user-attachments/assets/f845b70b-bfdf-4004-8427-3cfad4336f45)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
# Output
![image](https://github.com/user-attachments/assets/2a6481d7-05d6-41e4-94d5-d1352c845817)

```
sns.histplot(data = num_var, kde = True)
```
# Output
![image](https://github.com/user-attachments/assets/4851bde3-40ba-4114-bf40-b26ee3176c26)

```
df=pd.read_csv("/content/titanic_dataset (2).csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
# Output
![image](https://github.com/user-attachments/assets/baa6a9fa-0225-4a46-8c2b-cf0d157d7069)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
# Output
![image](https://github.com/user-attachments/assets/12dd68ef-dbf5-4d17-89c9-12b462a646df)

```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
# Output
![image](https://github.com/user-attachments/assets/e6073a47-ca8e-4bfb-8b37-08389d963114)

```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
# Output
![image](https://github.com/user-attachments/assets/b4a42ae6-072b-473f-9e69-fcf52772ed2f)

```
mart=pd.read_csv("/content/titanic_dataset (2).csv")
mart
```
# Output
![image](https://github.com/user-attachments/assets/76cb4c3e-80d1-4f9f-a233-82ffea2e499f)

```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
mart.head(10)
```
# Output
![image](https://github.com/user-attachments/assets/af8dcde6-f096-48a1-ade7-5e3dc87875fb)

```
sns.kdeplot(data=mart,x='PassengerId')
```
# Output
![image](https://github.com/user-attachments/assets/e98b60b7-5848-4f7a-8ec9-5728c103304a)

```
sns.kdeplot(data=mart,x='Age')
```
# Output
![image](https://github.com/user-attachments/assets/98af59c7-26a8-41ea-b8b6-f7419b536c5d)

```
sns.kdeplot(data=mart)
```
# Output
![image](https://github.com/user-attachments/assets/d8dd7515-42d2-4b47-9783-004a950e31ae)

```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
# Output
![image](https://github.com/user-attachments/assets/c802b1e2-25bc-4d4f-a65b-cd05c7232d66)

```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
# Output
![image](https://github.com/user-attachments/assets/93d71c15-f2e9-40a1-ad6f-70983f9d1263)

```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
# Output
![image](https://github.com/user-attachments/assets/f2527827-914c-4193-a79f-aa221a516353)

```
hm=sns.heatmap(data=data)
```
# Output
![image](https://github.com/user-attachments/assets/1acae807-5b22-4362-947b-ae99f3849097)

# Result:
 Thus, all the data visualization techniques of seaborn has been implemented successfully.
