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
from google.colab import drive
drive.mount('/content/drive')


![Screenshot 2024-12-20 105956](https://github.com/user-attachments/assets/48cefe42-c4fc-47e7-8667-a4e86c8a96e5)

import seaborn as sns
import matplotlib.pyplot as plt

x=[1,2,3,4,5]
y=[3,6,2,7,1]

sns.lineplot(x=x,y=y)


![Screenshot 2024-12-20 110009](https://github.com/user-attachments/assets/8160919c-6f3e-4126-87a0-9ded40efda0f)

df=sns.load_dataset("tips")
df


![Screenshot 2024-12-20 110020](https://github.com/user-attachments/assets/63471f63-1ff4-4d9b-a1db-ad1b43147bfc)

sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle='solid',legend="auto")


![Screenshot 2024-12-20 110031](https://github.com/user-attachments/assets/cdf44fb5-64e8-44a1-b134-861089259695)

x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]

sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("Multi-line Plot")
plt.xlabel('x-axis')
plt.ylabel('y-axis')


![Screenshot 2024-12-20 110043](https://github.com/user-attachments/assets/c28dee8d-8397-4b90-b072-b566ce74b3c4)

import seaborn as sns
import matplotlib.pyplot as plt
tips=sns.load_dataset("tips")
avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()


![Screenshot 2024-12-20 110106](https://github.com/user-attachments/assets/71303b3b-4cbb-4db9-8e81-a459df7586bc)

plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()


![Screenshot 2024-12-20 110117](https://github.com/user-attachments/assets/31e68232-7ca9-49e5-90e3-91f1601d3708)


avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()


![Screenshot 2024-12-20 110131](https://github.com/user-attachments/assets/b417ff07-b852-4599-bca0-252297083390)

p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill',width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip',width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()


![Screenshot 2024-12-20 110141](https://github.com/user-attachments/assets/3e290c73-c0d4-4bcb-9d6d-22e8bdac72ac)

years=range(2000, 2012)
apples=[0.895,0.91,0.919,0.926,0.929,0.931,0.934,0.936,0.937,0.9375,0.9372,0.939]
oranges=[0.962,0.941,0.930,0.923,0.918,0.908,0.907,0.904,0.901,0.898,0.9,0.896]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)


![Screenshot 2024-12-20 110153](https://github.com/user-attachments/assets/79b7f065-a4c4-4af4-9a3e-283a067221d9)

import seaborn as sns
dt=sns.load_dataset('tips')
sns.barplot(x='day',y='total_bill',hue='sex',data=dt,palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')


![Screenshot 2024-12-20 110205](https://github.com/user-attachments/assets/c64fc75b-1b46-42cd-b940-89c09d306121)

ls drive/MyDrive/titanic_dataset.csv


![Screenshot 2024-12-20 110215](https://github.com/user-attachments/assets/aa93e304-91df-47d0-9295-0e923fb73131)

import pandas as pd
tit=pd.read_csv("drive/MyDrive/titanic_dataset.csv")
tit


![Screenshot 2024-12-20 110231](https://github.com/user-attachments/assets/425f6944-61b8-478a-8656-9f943c52e71f)

plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=tit,palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")


![Screenshot 2024-12-20 110255](https://github.com/user-attachments/assets/deb2e975-3ece-4f24-8890-46915e1fc261)

plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=tit,palette='rainbow',hue='Pclass')
plt.title("Age of Passenger by Embarked Town,Divided by Class")


![Screenshot 2024-12-20 110309](https://github.com/user-attachments/assets/786639d0-a17c-49a3-a9b5-978baa3c774a)

import seaborn as sns
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill',y='tip',hue='sex',data=tips)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs Tip Amount')


![Screenshot 2024-12-20 110322](https://github.com/user-attachments/assets/5edcf49e-6ed7-4cea-928d-9bc1295e619e)

import numpy as np
import pandas as pd

np.random.seed(1)
num_var=np.random.randn(1000)
num_var=pd.Series(num_var,name="Numerocal Variable")
num_var


![Screenshot 2024-12-20 110337](https://github.com/user-attachments/assets/66de7602-8130-49b8-b03c-d75a2a56754b)

sns.histplot(data=num_var,kde=True)


![Screenshot 2024-12-20 110350](https://github.com/user-attachments/assets/3eefe367-19b2-4458-b10e-c070dca955fa)

df=pd.read_csv("drive/MyDrive/titanic_dataset.csv")
df


![Screenshot 2024-12-20 110406](https://github.com/user-attachments/assets/f2d4bf64-309b-43e8-94a7-4e5d2cf0645f)

sns.histplot(data=df,x="Pclass",hue="Survived",kde=True)


![Screenshot 2024-12-20 110425](https://github.com/user-attachments/assets/3bee4d5d-70e7-4b34-b490-bd4aeed24375)

import seaborn as sns
import matplotlib.pyplot as plt

np.random.seed(0)
marks=np.random.normal(loc=70,scale=10,size=100)
marks


![Screenshot 2024-12-20 110441](https://github.com/user-attachments/assets/ba7a176f-020f-49aa-9b93-3cc401ec4829)

sns.histplot(data=marks,bins=10,kde=True,stat='count',cumulative=False,multiple='stack',element='bars',palette='Set1',shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Students Markds')


![Screenshot 2024-12-20 110527](https://github.com/user-attachments/assets/ea70410b-78b5-493f-9eb8-2440ab2748b7)

tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])


![Screenshot 2024-12-20 110539](https://github.com/user-attachments/assets/c2d04d3a-9ceb-445c-b97d-469e49ea01c8)

sns.boxplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=0.6,boxprops={"facecolor":"lightblue","edgecolor":"darkblue"},
            whiskerprops={"color":"black","linestyle":"--","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.5})

            
![Screenshot 2024-12-20 110547](https://github.com/user-attachments/assets/d25c8c8f-8e46-463f-bb07-1bf09c7d6c09)

sns.boxplot(x="Pclass",y="Age",data=df,palette='rainbow')
plt.title("Age by Passenger Class, Titanic")


![Screenshot 2024-12-20 110637](https://github.com/user-attachments/assets/39994be6-b51b-4298-b5e9-8672c7681dd9)

sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,
palette='Set3',inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")


![Screenshot 2024-12-20 110647](https://github.com/user-attachments/assets/457e5ac0-e5ca-4441-b863-1c6d2a4671d4)

import seaborn as sns
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip)


![Screenshot 2024-12-20 110656](https://github.com/user-attachments/assets/4751261f-4999-4b23-ad6b-15d83cdcc18e)

tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])


![Screenshot 2024-12-20 110705](https://github.com/user-attachments/assets/2e0b4efd-adc7-45a9-a790-478e4a24405f)

sns.set(style='whitegrid')
tips=sns.load_dataset("tips")
sns.violinplot(x='tip',y='day',data=tip)


![Screenshot 2024-12-20 110732](https://github.com/user-attachments/assets/3197bd42-04e7-41ab-a1e1-d61d2064a927)

sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)
multiple='stack'
multiple='layer'


![Screenshot 2024-12-20 110743](https://github.com/user-attachments/assets/de23a1e9-55a9-4fa0-8885-244e414bd4da)

sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)


![Screenshot 2024-12-20 110756](https://github.com/user-attachments/assets/5ab78eac-6acd-43df-8c75-d60b2e3dce2c)

sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set2',alpha=0.8)


![Screenshot 2024-12-20 110808](https://github.com/user-attachments/assets/6ba80cde-178e-4ebf-a1b4-9aa0b458accb)

sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set2',alpha=0.8)


![Screenshot 2024-12-20 110819](https://github.com/user-attachments/assets/94d27803-8cc7-4152-90dc-ae31efd3c2e1)

mart=pd.read_csv("drive/MyDrive/supermarket.csv")
mart


![Screenshot 2024-12-20 110841](https://github.com/user-attachments/assets/d8cae403-d240-47cd-ac56-cb8ffb41c7d3)

sns.kdeplot(data=mart,x='Total')


![Screenshot 2024-12-20 110850](https://github.com/user-attachments/assets/5cbd0945-63f8-429e-8144-a49383025c0d)

sns.kdeplot(data=mart,x='Unit price')


![Screenshot 2024-12-20 110859](https://github.com/user-attachments/assets/128560af-e81a-4951-886b-7334314d4774)

sns.kdeplot(data=mart)


![Screenshot 2024-12-20 110909](https://github.com/user-attachments/assets/8d0a0e10-8a3e-4c93-b94c-45dcb9921997)

sns.kdeplot(data=mart,x='Total',hue='Payment',multiple='stack',linewidth=5,palette='Dark2',alpha=0.5)


![Screenshot 2024-12-20 110917](https://github.com/user-attachments/assets/75453df8-a070-4592-9a7f-0f062e0c91e0)

sns.kdeplot(data=mart,x='Unit price',y='gross income')


![Screenshot 2024-12-20 110927](https://github.com/user-attachments/assets/01ebb1e9-9ac0-4d65-a0e7-0489032622bc)

data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted:\n")
print(data)


![Screenshot 2024-12-20 110937](https://github.com/user-attachments/assets/ba34e18f-e6b6-49af-8c5e-6d8195437006)

hm=sns.heatmap(data=data,annot=True)


![Screenshot 2024-12-20 110948](https://github.com/user-attachments/assets/97c26102-eff1-4a75-b2c5-0bcd276a7f97)

hm=sns.heatmap(data=data)


![Screenshot 2024-12-20 111001](https://github.com/user-attachments/assets/e0afc5c2-4d3d-4356-bddc-012923f9110e)

tips=sns.load_dataset("tips")
numeric_cols=tips.select_dtypes(include=np.number).columns
corr=tips[numeric_cols].corr()

sns.heatmap(corr,annot=True,cmap="plasma",linewidths=0.5)


![Screenshot 2024-12-20 111013](https://github.com/user-attachments/assets/a35b1ec4-7038-4b70-8111-c28945baf007)

 Include the necessary coding and corresponding screenshots

# Result:
 The above code is excuted succeessfully.
