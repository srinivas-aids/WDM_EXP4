### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 10.03.24
```
Name: srinivas.u
Reg.No:212221230108
```
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
# Visitor segmentation based on characteristics
import pandas as pd
import matplotlib.pyplot as plt

# read the data
visitor_df=pd.read_csv('clustervisitor.csv')

# Perform segmentation based on characteristics (e.g., age groups)
age_groups={
    'Young':(visitor_df['Age']<=30),
    'Middle-aged':((visitor_df['Age']>30) & (visitor_df['Age'] <=50)),
    'Eldery':(visitor_df['Age'] > 50)
}

for group,condition in age_groups.items():
  visitors_in_group=visitor_df[condition]
  print(f"Visitors in {group} age group")
  print(visitors_in_group)
  print()
```
### Output:
![image](https://github.com/Hariharan-061102/WDM_EXP4/assets/93427270/6792d05a-079a-4312-9180-7a55f3d6a9a5)
![image](https://github.com/Hariharan-061102/WDM_EXP4/assets/93427270/bac58835-8c8b-4a39-a22f-cd40b5160cb4)
![image](https://github.com/Hariharan-061102/WDM_EXP4/assets/93427270/0d9fae44-5e51-4cf0-a846-95ccaf0f6d93)



### Visualization:
```python
# Create a list to store counts of visitors in each age group
visitor_count= []

# Count visitors in each age group
for group,condition in age_groups.items():
  visitors_in_group=visitor_df[condition]
  visitor_count.append(len(visitors_in_group))
    
# Define age group labels and plot a bar chart
age_group_labels=list(age_groups.keys())
plt.figure(figsize=(8,6))
plt.bar(age_group_labels,visitor_count,color='skyblue')
plt.xlabel('Age Grouping')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
![image](https://github.com/Hariharan-061102/WDM_EXP4/assets/93427270/cf676403-9300-4b74-9f5c-b4591322905f)


### Result:
Thus Cluster and Visitor Segmentation for Navigation pattern has been implemented successfully.
