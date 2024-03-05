
In the comprehensive dashboard, I integrated key business metrics using the Gauge card to present Total Sales, Operating Profit, and Average Operating Profit. Additionally, for a more detailed analysis, I incorporated a slicer functionality to dissect sales, region, and retailer data by quarter, providing a granular view of performance over time.


```python
#Import Packages and CSV dataset
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv ('/content/drive/MyDrive/data /Adidas_Sales_Datasets.csv')
print (df.head ())
print (df.info ())

# Pie Chart Sales by Retailer
sales_by_retailer = df.groupby ('Retailer')['Total Sales'].sum()
print (sales_by_retailer)

labels = sales_by_retailer.index
fig, ax = plt.subplots()
ax.pie (sales_by_retailer, labels = labels, autopct = '%1.1f%%')
plt.show ()

# Bar Chart Sales by Region
sales_by_region = df.groupby ("Region") ["Total Sales"].sum ()
print (sales_by_region)

labels = sales_by_region.index
values = sales_by_region.values

plt.bar (labels, values)

plt.xlabel ('Region')
plt.ylabel ('Total Sales')
plt.xticks(rotation = 45)
plt.title ('Totals by Sale Regions')

plt.show ()
```
