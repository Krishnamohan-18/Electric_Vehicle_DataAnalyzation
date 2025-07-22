# Electric_Vehicle_DataAnalyzation
**Project Title:** Electric Vehicle Data Analysis  
This project explores and analyzes electric vehicle registration and population trends using publicly available datasets.  
# Objective   
1.Understand EV adoption trends across regions and time.  
2.Identify top EV models, manufacturers, and growth patterns.  
3.Use data visualization to make insights actionable.  
# Dataset  
**Source**:Kaggle  
**Tools Used**    
- Python (Pandas, Matplotlib, Seaborn)       
- Jupyter Notebook     
**Task 1.**  DataSetup    
```python  
!pip install pandas  
!pip install numpy 
import matplotlib.pyplot as plt 
import seaborn as sns  
import pandas as pd  
import numpy as np  
df = pd.read_csv("Electric_Vehicle_Population_Data.csv")  
df.info()  
```
**Task 2.** Dataset Structure and Dimensions,Preview the Dataset
 
```python  
df.columns    
df.shape    
df.head()  
df.tail()  
```
**Task 3.Data Cleaning**  
1.How many missing values exist in the dataset, and in which columns? 
```python
total_missing_values = df.isna().sum().sum()  
missing_values _in each column = df.isna().sum()  
missing_values _in each column [missing_values _in each column>0]  
```
2.How should missing or zero values in the Base MSRP and Electric Range columns be handled.  
 **Base MSRP - Missing Values Handling**
->Here Zero Values are considering as Missing Values and converting Zero values in to Missing values and replacing NAN values with median  
```python
print("initial nan count:",df['Base MSRP'].isnull().sum())  
zero_count = (df["Base MSRP"]==0).sum()  
print("initial zer count:",zero_count )  
print("median before converting zer to nan :",df['Base MSRP'].median())  
df.loc[df['Base MSRP'] == 0, 'Base MSRP'] = np.nan  
zero_count = (df["Base MSRP"]==0).sum()  
print("after conversion zero count:",zero_count )  
```
NOTE: After converting zero values into nan values and after when we replace nan values with median for the whole data  but NAN is replaced
 to over come this  
```python
median_value=(df.loc[df["Base MSRP"]>0,"Base MSRP"].median())  
if not np.isnan(median_value):  
    df['Base MSRP'].fillna(median_value,inplace = True)  
else:  
    print("error:median is NAN  Value")  
print("nan values after replacing with median value:",df['Base MSRP'].isnull().sum())  
print(df['Base MSRP'].median())  
```
**Electric Range -Missing Values Handling.**  
```python  
 print("median value:",df.loc[df["Electric Range"]>0,"Electric Range"].median())  
df.loc[df['Electric Range'] == 0, 'Electric Range'] = np.nan  
zero_count = (df["Electric Range"]==0).sum()  
df["Electric Range"].isna().sum()  
median_value=(df.loc[df["Electric Range"]>0,"Electric Range"].median())  
if not np.isnan(median_value):  
    df["Electric Range"].fillna(median_value,inplace = True)  
else:  
    print("error:median is NAN  Value")  

 ```
  

