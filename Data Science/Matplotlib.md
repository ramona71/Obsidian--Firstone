- https://matplotlib.org/stable/users/explain/quick_start.html
- Data visualization library
- static, animated and interactive visualizations
- pyplot -> library ->most visualization are present in this
```python
!pip install matplotlib
pip show matplotlib

x=[1,2,3,4,5]
y=[1,4,9,16,25]
  
# a line plot
plt.plot(x,y)
plt.xlabel('X-Axis')
plt.ylabel('Y-Axis')
plt.title('Entire graph label')
plt.show()   # to show

# custom line plot
plt.plot(x,y, color='pink', linestyle= '-.', marker='x',linewidth='3', markersize='10')
plt.grid('True')
```
- Multiple Plots
```python
x = [1, 2, 3, 4, 5]
y1 = [1, 4, 9, 16, 25]
y2 = [1, 2, 3, 4, 5]
  
plt.figure(figsize=(9,5))
plt.subplot(1,2,1)
plt.plot(x,y1, color='red')
  
plt.subplot(1,2,2)
plt.plot(x,y2, color='blue')
```
- Bar plot
```python
categories=['A','B','C','D','E']
values=[5,7,3,8,6]
  
plt.bar(categories, values, color='purple')
plt.ylabel('holes')
plt.title('Mens underwear')
plt.xlabel('names')
```
- histograms
```python
data = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5]
plt.hist(data,bins=5, color='pink', edgecolor='red')
```
- scatterplot
```python
x = [1, 2, 3, 4, 5]
y = [2, 3, 4, 5, 6]
  
plt.scatter(x,y,color="blue",marker='x')
```
- pychart
```python
labels=['A','B','C','D']
sizes=[30,20,40,10]
colors=['gold','yellowgreen','lightcoral','lightskyblue']
explode=(0.2,0,0,0) ##move out the 1st slice
  
##create apie chart
plt.pie(sizes,explode=explode,labels=labels,colors=colors,autopct="%1.1f%%",shadow=True)
```
- sales data visulisation
```python
## Sales Data Visualization

import pandas as pd
sales_data_df=pd.read_csv('sales_data.csv')
sales_data_df.head(5)
sales_data_df.info()

total_sales_by_product=sales_data_df.groupby('Product Category')['Total Revenue'].sum()
print(total_sales_by_product)
total_sales_by_product.plot(kind='bar',color='teal')

## plot sales trend over time
sales_trend=sales_data_df.groupby('Date')['Total Revenue'].sum().reset_index()
plt.plot(sales_trend['Date'],sales_trend['Total Revenue'])
```