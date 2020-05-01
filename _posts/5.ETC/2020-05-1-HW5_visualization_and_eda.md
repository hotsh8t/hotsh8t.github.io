---
title: "HW5_visualization_and_eda"
excerpt: "HW5_visualization_and_eda" 
toc: true
toc_sticky: true
categories:
  - ETC
tags:
  - ETC
  - git
 
---
# Homework Assignment #5 : Visualization and EDA


```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

%matplotlib inline
```

### From the given data (covid20200416_rev.csv), write your codes according to the following questions.


```python
df_covid = pd.read_csv('./covid20200416_rev.csv')
print(len(df_covid))
df_covid.head()
```


212





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>total_cases</th>
      <th>total_deaths</th>
      <th>total_recovered</th>
      <th>Tot_cases_per_1Mpop</th>
      <th>Deaths_per_1Mpop</th>
      <th>region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>USA</td>
      <td>644089</td>
      <td>28529</td>
      <td>48701</td>
      <td>1946.0</td>
      <td>86.0</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Spain</td>
      <td>180659</td>
      <td>18812</td>
      <td>70853</td>
      <td>3864.0</td>
      <td>402.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Italy</td>
      <td>165155</td>
      <td>21645</td>
      <td>38092</td>
      <td>2732.0</td>
      <td>358.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>3</th>
      <td>France</td>
      <td>147863</td>
      <td>17167</td>
      <td>30955</td>
      <td>2265.0</td>
      <td>263.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Germany</td>
      <td>134753</td>
      <td>3804</td>
      <td>72600</td>	
      <td>1608.0</td>
      <td>45.0</td>
      <td>Europe</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_covid.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;    
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>total_cases</th>
      <th>total_deaths</th>
      <th>total_recovered</th>
      <th>Tot_cases_per_1Mpop</th>
      <th>Deaths_per_1Mpop</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>212.000000</td>
      <td>212.000000</td>
      <td>212.000000</td>
      <td>210.000000</td>
      <td>162.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>9826.905660</td>
      <td>634.976415</td>
      <td>2407.268868</td>
      <td>626.120143</td>
      <td>33.438457</td>
    </tr>
    <tr>
      <th>std</th>
      <td>50052.898899</td>
      <td>3155.560189</td>
      <td>10488.024252</td>
      <td>1463.639958</td>
      <td>107.465073</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.030000</td>
      <td>0.030000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>39.500000</td>
      <td>1.000000</td>
      <td>5.000000</td>
      <td>18.000000</td>
      <td>0.600000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>382.500000</td>
      <td>6.000000</td>
      <td>67.000000</td>
      <td>104.500000</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2270.250000</td>
      <td>52.750000</td>
      <td>346.250000</td>
      <td>465.750000</td>
      <td>17.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>644089.000000</td>
      <td>28529.000000</td>
      <td>77892.000000</td>
      <td>11582.000000</td>
      <td>1061.000000</td>
    </tr>
  </tbody>
</table>
</div>



#### (1) Visualize the mean total_cases according to each region by the bar chart. 


```python
# your code here
mean_total_cases_by_region = df_covid.groupby('region').total_cases.mean()
mean_total_cases_by_region
mean_total_cases_by_region.sort_values(inplace=True, ascending=True)
x = mean_total_cases_by_region.index.tolist()
y = mean_total_cases_by_region.values.tolist()
# x1 = list(mean_total_cases_by_region.index)
# y1 = list(mean_total_cases_by_region.values)
#print(type(x), y, type(x1), y1)

plt.title('Mean Total Cases by Each Region')
plt.xlabel("Region")
plt.ylabel("Mean cases")
#plt.barh(x,y)
plt.bar(x,y)
plt.xticks(rotation=-15)
plt.show()
```


![output_6_0](https://user-images.githubusercontent.com/64456846/80827844-5075e580-8c1f-11ea-9b34-c642649bd820.png)


#### (2) Plot the distribution(histogram) of total cases per 1M population (Tot_cases_per_1Mpop) using Seaborn package.
   * Note: Before applying the visualization for distribution, you may need to filter out rows of missing value (NaN).


```python
# your code here 2-1 : find NaN
print("duplicated data?:", df_covid.duplicated().sum())
sns.heatmap(df_covid.isnull(), cbar=False)
plt.show()
```


duplicated data?: 0



![output_8_1](https://user-images.githubusercontent.com/64456846/80827879-62578880-8c1f-11ea-8bf0-0d0c2932170b.png)


```python
# your code here 2-2 :dropna 
df_covid = df_covid.dropna(subset=['Tot_cases_per_1Mpop'], axis = 'index')

d = df_covid.Tot_cases_per_1Mpop.isnull()
# len(d)
count = 0 ;
for i in range(0, len(d)):
    if d.iloc[i] == True:
        count += 1 
print("NaN of 'Tot_cases_per_1Mpop':", count)

sns.heatmap(df_covid.isnull(), cbar=False)
plt.show()
```


NaN of 'Tot_cases_per_1Mpop': 0



![output_9_1](https://user-images.githubusercontent.com/64456846/80827906-6d121d80-8c1f-11ea-9f67-9f3497289514.png)




```python
# your code here 2-3 : draw plot
sns.distplot(df_covid['Tot_cases_per_1Mpop'])
plt.show()
```


![output_10_0](https://user-images.githubusercontent.com/64456846/80827933-7a2f0c80-8c1f-11ea-872e-b78eb9f170c4.png)


#### (3) Plot the scatter plot according to the following conditions
   * x values: 'total_cases'
   * y values: 'total_deaths'



```python
# your code here 3-1 : describe dataframe
df_covid.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>total_cases</th>
      <th>total_deaths</th>
      <th>total_recovered</th>
      <th>Tot_cases_per_1Mpop</th>
      <th>Deaths_per_1Mpop</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>210.000000</td>
      <td>210.000000</td>
      <td>210.000000</td>
      <td>210.000000</td>
      <td>162.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>9917.061905</td>
      <td>640.957143</td>
      <td>2427.128571</td>
      <td>626.120143</td>
      <td>33.438457</td>
    </tr>
    <tr>
      <th>std</th>
      <td>50283.196920</td>
      <td>3170.021744</td>
      <td>10536.046314</td>
      <td>1463.639958</td>
      <td>107.465073</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.030000</td>
      <td>0.030000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>41.500000</td>
      <td>1.000000</td>
      <td>5.250000</td>
      <td>18.000000</td>
      <td>0.600000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>382.500000</td>
      <td>6.000000</td>
      <td>67.000000</td>
      <td>104.500000</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2426.750000</td>
      <td>58.250000</td>
      <td>333.000000</td>
      <td>465.750000</td>
      <td>17.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>644089.000000</td>
      <td>28529.000000</td>
      <td>77892.000000</td>
      <td>11582.000000</td>
      <td>1061.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# your code here 3-2 : draw plot

x = df_covid['total_cases']
y = df_covid['total_deaths']

plt.scatter(x, y, marker = '+', s=150, color='red')
plt.show()


```


![output_13_0](https://user-images.githubusercontent.com/64456846/80827944-8024ed80-8c1f-11ea-93cb-78a589218023.png)


#### (4) Plot the heatmap of correlations among all numerical variables. Which variable (column) is the most correlated with the value "total_cases"?


```python
# your code here : 4-1 calculate corr
df_corr = df_covid[:]
df_corr.corr()

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>total_cases</th>
      <th>total_deaths</th>
      <th>total_recovered</th>
      <th>Tot_cases_per_1Mpop</th>
      <th>Deaths_per_1Mpop</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>total_cases</th>
      <td>1.000000</td>
      <td>0.885806</td>
      <td>0.652631</td>
      <td>0.156965</td>
      <td>0.220542</td>
    </tr>
    <tr>
      <th>total_deaths</th>
      <td>0.885806</td>
      <td>1.000000</td>
      <td>0.664417</td>
      <td>0.209220</td>
      <td>0.379455</td>
    </tr>
    <tr>
      <th>total_recovered</th>
      <td>0.652631</td>
      <td>0.664417</td>
      <td>1.000000</td>
      <td>0.160642</td>
      <td>0.244011</td>
    </tr>
    <tr>
      <th>Tot_cases_per_1Mpop</th>
      <td>0.156965</td>
      <td>0.209220</td>
      <td>0.160642</td>
      <td>1.000000</td>
      <td>0.852964</td>
    </tr>
    <tr>
      <th>Deaths_per_1Mpop</th>
      <td>0.220542</td>
      <td>0.379455</td>
      <td>0.244011</td>
      <td>0.852964</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# your code here :4-2 draw heatmap
h = sns.heatmap(df_corr.corr(), annot=True, cmap='RdYlGn_r')
h.set_xticklabels(h.get_xticklabels(),rotation=-15, fontsize='small')
plt.show()
```


![output_16_0](https://user-images.githubusercontent.com/64456846/80827980-8adf8280-8c1f-11ea-86d7-4910059a6ef8.png)


### 5) Plot the boxplots of mean total_cases according to each "region". 


```python
# your code here
sns.catplot(x='region', y='total_cases', kind='box', data=df_covid)
plt.xticks(rotation = -15)
plt.show()
```



![output_18_0](https://user-images.githubusercontent.com/64456846/80828017-95018100-8c1f-11ea-8955-d3208a2f6200.png)



#### Open question: Can you find any other insight from the data?


```python
#your code here : Open question-1
sns.pairplot(data=df_covid, hue='region')
plt.show()
```
 

![output_20_1](https://user-images.githubusercontent.com/64456846/80828058-a64a8d80-8c1f-11ea-8998-41fb81411ff0.png)
nstead? -->



```python
#your code here : Open question-2
df_covid.sort_values(by='total_deaths', ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>total_cases</th>
      <th>total_deaths</th>
      <th>total_recovered</th>
      <th>Tot_cases_per_1Mpop</th>
      <th>Deaths_per_1Mpop</th>
      <th>region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>USA</td>
      <td>644089</td>
      <td>28529</td>
      <td>48701</td>
      <td>1946.00</td>
      <td>86.0</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Italy</td>
      <td>165155</td>
      <td>21645</td>
      <td>38092</td>
      <td>2732.00</td>
      <td>358.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Spain</td>
      <td>180659</td>
      <td>18812</td>
      <td>70853</td>
      <td>3864.00</td>
      <td>402.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>3</th>
      <td>France</td>
      <td>147863</td>
      <td>17167</td>
      <td>30955</td>
      <td>2265.00</td>
      <td>263.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>5</th>
      <td>UK</td>
      <td>98476</td>
      <td>12868</td>
      <td>344</td>
      <td>1451.00</td>
      <td>190.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>175</th>
      <td>Nepal</td>
      <td>16</td>
      <td>0</td>
      <td>1</td>
      <td>0.50</td>
      <td>NaN</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>176</th>
      <td>Dominica</td>
      <td>16</td>
      <td>0</td>
      <td>8</td>
      <td>222.00</td>
      <td>NaN</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>178</th>
      <td>Namibia</td>
      <td>16</td>
      <td>0</td>
      <td>3</td>
      <td>6.00</td>
      <td>NaN</td>
      <td>Africa</td>
    </tr>
    <tr>
      <th>179</th>
      <td>Saint Lucia</td>
      <td>15</td>
      <td>0</td>
      <td>11</td>
      <td>82.00</td>
      <td>NaN</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>211</th>
      <td>Yemen</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0.03</td>
      <td>NaN</td>
      <td>Asia</td>
    </tr>
  </tbody>
</table>
<p>210 rows × 7 columns</p>
</div>




```python
#your code here : Open question-3
df_covid.sort_values(by='total_recovered', ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>country</th>
      <th>total_cases</th>
      <th>total_deaths</th>
      <th>total_recovered</th>
      <th>Tot_cases_per_1Mpop</th>
      <th>Deaths_per_1Mpop</th>
      <th>region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6</th>
      <td>China</td>
      <td>82341</td>
      <td>3342</td>
      <td>77892</td>
      <td>57.00</td>
      <td>2.0</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Germany</td>
      <td>134753</td>
      <td>3804</td>
      <td>72600</td>
      <td>1608.00</td>
      <td>45.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Spain</td>
      <td>180659</td>
      <td>18812</td>
      <td>70853</td>
      <td>3864.00</td>
      <td>402.0</td>
      <td>Europe</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Iran</td>
      <td>76389</td>
      <td>4777</td>
      <td>49933</td>
      <td>909.00</td>
      <td>57.0</td>
      <td>Asia</td>
    </tr>
    <tr>
      <th>0</th>
      <td>USA</td>
      <td>644089</td>
      <td>28529</td>
      <td>48701</td>
      <td>1946.00</td>
      <td>86.0</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>172</th>
      <td>Belize</td>
      <td>18</td>
      <td>2</td>
      <td>0</td>
      <td>45.00</td>
      <td>5.0</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>158</th>
      <td>Haiti</td>
      <td>41</td>
      <td>3</td>
      <td>0</td>
      <td>4.00</td>
      <td>0.3</td>
      <td>North America</td>
    </tr>
    <tr>
      <th>157</th>
      <td>Guinea-Bissau</td>
      <td>43</td>
      <td>0</td>
      <td>0</td>
      <td>22.00</td>
      <td>NaN</td>
      <td>Africa</td>
    </tr>
    <tr>
      <th>149</th>
      <td>French Polynesia</td>
      <td>55</td>
      <td>0</td>
      <td>0</td>
      <td>196.00</td>
      <td>NaN</td>
      <td>Oceania</td>
    </tr>
    <tr>
      <th>211</th>
      <td>Yemen</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0.03</td>
      <td>NaN</td>
      <td>Asia</td>
    </tr>
  </tbody>
</table>
<p>210 rows × 7 columns</p>
</div>




```python
#your code here : Open question-4
df_covid_no_usa = df_covid.drop(df_covid[df_covid['country'] == 'USA'].index)
sns.pairplot(data=df_covid_no_usa, hue='region')
plt.show()
```
 


![output_23_1](https://user-images.githubusercontent.com/64456846/80828143-ba8e8a80-8c1f-11ea-8418-a85f2af19889.png)


#### 결론
* North America(미국) 이 다른 나라에 비해 월등하게 높은 감염이 일어나고 있다.   
* 미국 케이스를 제외하면 total cases 기준 유럽국가들의 사망률(특히 이탈리아)이 높다. 
* 아시아 국가들(중국, 이란)이 동일 감염case에 대해 recover 되는 확률이 높은 편이다

 
---

 
