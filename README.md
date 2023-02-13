# Booston_dataset-EDA-in-python
booston house data analysis with python in EDA
from google.colab import drive
drive.mount('/content/drive')

import pandas as pd
data=pd.read_csv('/content/drive/MyDrive/train/Boston.csv') 
data

#DataTypes
data.dtypes

#Data Shape
data.shape

#About  Information of the data
data.info()

#Describe the dataset
data.describe()

# Commented out IPython magic to ensure Python compatibility.
#libraries for visualization
import matplotlib.pyplot as plt
# %matplotlib inline
import seaborn as sns



#univeriate analysis using pyplot
plt.hist(data["AGE"])

plt.figure(figsize=(10,10))
df1=data[["AGE","DIS"]]
plt.title('Box plot for 2 variables')
plt.boxplot (df1.values,labels=['AGE','DIS'])

#barplot is only applicable for univariate and only catogorical data 
#using matplotlib
data["RAD"].value_counts().plot.bar()

#multivariate 
#using matplotlib
#scattor is applicable only for univariate
plt.scatter(data.index,data["AGE","DIS"])
plt.show()

corelation=data.corr()
sns.heatmap(corelation,xticklabels=corelation.columns,yticklabels=corelation.columns,annot=True)
