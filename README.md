# UBER-ANALYSIS-PROJECT


## AIM:
The analysis aims to provide valuable insights for various stakeholders. City planners
can utilize the findings to optimize public transport infrastructure and address traffic
congestion issues. Uber itself can benefit from understanding user behavior to improve
service efficiency and dynamic pricing strategies. Ultimately, this project contributes to
a deeper understanding of ride-sharing.


## PROBLEM STATEMENT
The ever-growing popularity of ride-sharing services like Uber has brought both convenience and challenges to urban transportation. While offering on-demand mobility, Uber also contributes to traffic congestion and raises questions about pricing fairness and service efficiency.
This analysis aims to address these challenges by leveraging the vast amount of data
generated by Uber trips.

## PROGRAM

```
import pandas as pd
import numpy as np

#Visualization modules
import seaborn as sns
data = pd.read_csv("/content/uber-raw-data-sep14.csv")
data
data["Date/Time"] = data["Date/Time"].map(pd.to_datetime)
data.head()
data["Day"] = data["Date/Time"].apply(lambda x: x.day)
data["Weekday"] = data["Date/Time"].apply(lambda x: x.weekday())
data["Hour"] = data["Date/Time"].apply(lambda x: x.hour)
print(data.head())
sns.set(rc={'figure.figsize':(12, 10)})
sns.distplot(data["Day"])
sns.distplot(data["Hour"])
sns.distplot(data["Weekday"])

df = data.groupby(["Weekday", "Hour"]).apply(lambda x: len(x))
df = df.unstack()
sns.heatmap(df, annot=False)
import matplotlib.pyplot as plt # imports the matplotlib.pyplot module

data.plot(kind='scatter', x='Lon', y='Lat', alpha=0.4, s=data['Day'], label='Uber Trips',
figsize=(12, 8), cmap=plt.get_cmap('jet'))
plt.title("Uber Trips Analysis")
plt.legend()
plt.show()

```
## OUTPUT
![Screenshot 2024-10-20 101614](https://github.com/user-attachments/assets/85f9013e-fee5-43d3-abf1-0c1ab73dd031)





![Screenshot 2024-10-20 101619](https://github.com/user-attachments/assets/03989823-a08c-4acf-9348-adfb1760c1e4)



![Screenshot 2024-10-20 101623](https://github.com/user-attachments/assets/4281474d-0710-45a7-a389-a39971a2a503)

![Screenshot 2024-10-20 101642](https://github.com/user-attachments/assets/548331b0-6505-4548-887f-0b56df9db1bd)

![Screenshot 2024-10-20 101650](https://github.com/user-attachments/assets/a9e47df3-a2d8-49ea-a75c-92487e104413)
![Screenshot 2024-10-20 101656](https://github.com/user-attachments/assets/9c25da71-82f7-4a3e-b339-b31f04dc1e57)
![Screenshot 2024-10-20 101703](https://github.com/user-attachments/assets/e6ef09e2-4490-40fd-83a5-a3209a058a19)
![Screenshot 2024-10-20 101708](https://github.com/user-attachments/assets/4a67676e-41c7-46bc-84c2-09f575a7f887)

## RESULT
Thus implementation of Analysing Uber trip data can reveal interesting travel patterns in a cityhas been executed succesfully.

