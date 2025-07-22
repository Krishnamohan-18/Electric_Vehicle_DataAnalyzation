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


  
