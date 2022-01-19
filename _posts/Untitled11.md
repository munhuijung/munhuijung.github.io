```python
x=emp.groupby('job')['sal'].max().reset_index()
x.columns = ['job','maxsal']
x
#df.groupby('그룹핑할 컬럼')['값'].어떻게할까?().reset_index()
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
      <th>job</th>
      <th>maxsal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>ANALYST</td>
      <td>3000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>CLERK</td>
      <td>1300</td>
    </tr>
    <tr>
      <th>2</th>
      <td>MANAGER</td>
      <td>2975</td>
    </tr>
    <tr>
      <th>3</th>
      <td>PRESIDENT</td>
      <td>5000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>SALESMAN</td>
      <td>1600</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.groupby('deptno')['sal'].sum().reset_index()
x.columns=['deptno','sumsal']
x
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
      <th>deptno</th>
      <th>sumsal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>10</td>
      <td>8750</td>
    </tr>
    <tr>
      <th>1</th>
      <td>20</td>
      <td>10875</td>
    </tr>
    <tr>
      <th>2</th>
      <td>30</td>
      <td>9400</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.groupby('deptno')['sal'].sum().reset_index()
x.columns=['deptno','sumsal']
x.sort_values(by='sumsal',ascending=False)

#높은 순 정렬 =>df.sort_values(by='컬럼',ascending=False)
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
      <th>deptno</th>
      <th>sumsal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>20</td>
      <td>10875</td>
    </tr>
    <tr>
      <th>2</th>
      <td>30</td>
      <td>9400</td>
    </tr>
    <tr>
      <th>0</th>
      <td>10</td>
      <td>8750</td>
    </tr>
  </tbody>
</table>
</div>




```python
x = emp.groupby('job')['empno'].count().reset_index()
x.columns=['job','cnt']
x.sort_values('cnt',ascending=False)
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
      <th>job</th>
      <th>cnt</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>CLERK</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>SALESMAN</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>MANAGER</td>
      <td>3</td>
    </tr>
    <tr>
      <th>0</th>
      <td>ANALYST</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>PRESIDENT</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.groupby('job')['sal'].sum().reset_index()
x.columns=['job','sumsal']
x[['job','sumsal']][x['sumsal']>=5000]

#x[['원하는 컬럼']][df[조건]]
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
      <th>job</th>
      <th>sumsal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>ANALYST</td>
      <td>6000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>MANAGER</td>
      <td>8275</td>
    </tr>
    <tr>
      <th>3</th>
      <td>PRESIDENT</td>
      <td>5000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>SALESMAN</td>
      <td>5600</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.groupby('job')['sal'].sum().reset_index()
x.columns=['job','sumsal']
x[['job','sumsal']][x['sumsal']>=5000]
x.sort_values(by='sumsal',ascending=False)
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
      <th>job</th>
      <th>sumsal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>MANAGER</td>
      <td>8275</td>
    </tr>
    <tr>
      <th>0</th>
      <td>ANALYST</td>
      <td>6000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>SALESMAN</td>
      <td>5600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>PRESIDENT</td>
      <td>5000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>CLERK</td>
      <td>4150</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.groupby('job')['sal'].sum().reset_index()
x.columns=['job','sumsal']
x2=x[['job','sumsal']][x['sumsal']>=5000]
x3=x2[['job','sumsal']][x['job']!='SALESMAN']
x3.sort_values(by='sumsal',ascending=False)
```

    C:\Users\gram\AppData\Local\Temp/ipykernel_10212/3420407609.py:4: UserWarning: Boolean Series key will be reindexed to match DataFrame index.
      x3=x2[['job','sumsal']][x['job']!='SALESMAN']
    




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
      <th>job</th>
      <th>sumsal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>MANAGER</td>
      <td>8275</td>
    </tr>
    <tr>
      <th>0</th>
      <td>ANALYST</td>
      <td>6000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>PRESIDENT</td>
      <td>5000</td>
    </tr>
  </tbody>
</table>
</div>




```python
import datetime 

emp['hiredate']=pd.to_datetime(emp['hiredate'])
emp['hiredate'].dt.year
#1> pd.to_date(컬럼) 2> 컬럼.dt.원하는 형식 
```




    0     1981
    1     1981
    2     1981
    3     1981
    4     1981
    5     1981
    6     1981
    7     1981
    8     1981
    9     1981
    10    1980
    11    1982
    12    1983
    13    1982
    Name: hiredate, dtype: int64




```python
emp['hiredate']=pd.to_datetime(emp['hiredate'])
emp['hire_year']=emp['hiredate'].dt.year
emp.groupby(['hire_year','deptno'])['sal'].sum().reset_index()

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
      <th>hire_year</th>
      <th>deptno</th>
      <th>sal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1980</td>
      <td>20</td>
      <td>800</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1981</td>
      <td>10</td>
      <td>7450</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1981</td>
      <td>20</td>
      <td>5975</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1981</td>
      <td>30</td>
      <td>9400</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1982</td>
      <td>10</td>
      <td>1300</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1982</td>
      <td>20</td>
      <td>3000</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1983</td>
      <td>20</td>
      <td>1100</td>
    </tr>
  </tbody>
</table>
</div>




```python
emp.pivot_table(columns = 'deptno',aggfunc='sum')
#pivot_table(index=   ,columns=   ,aggfunc=    )=> aggfunc 미지정시 평균값(mean)
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
      <th>deptno</th>
      <th>10</th>
      <th>20</th>
      <th>30</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Unnamed: 0</th>
      <td>15.0</td>
      <td>45.0</td>
      <td>31.0</td>
    </tr>
    <tr>
      <th>comm</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>2200.0</td>
    </tr>
    <tr>
      <th>empno</th>
      <td>23555.0</td>
      <td>38501.0</td>
      <td>46116.0</td>
    </tr>
    <tr>
      <th>hire_year</th>
      <td>5944.0</td>
      <td>9907.0</td>
      <td>11886.0</td>
    </tr>
    <tr>
      <th>mgr</th>
      <td>15621.0</td>
      <td>38661.0</td>
      <td>46329.0</td>
    </tr>
    <tr>
      <th>sal</th>
      <td>8750.0</td>
      <td>10875.0</td>
      <td>9400.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.pivot_table(columns = 'deptno',aggfunc='sum')
x.iloc[[5],0:]   #번호로 출력하기 df.iloc[행,열]
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
      <th>deptno</th>
      <th>10</th>
      <th>20</th>
      <th>30</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>sal</th>
      <td>8750.0</td>
      <td>10875.0</td>
      <td>9400.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.pivot_table(columns='job',aggfunc='count')
x=x.iloc[[0],0:]
x.index=['cnt']
x
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
      <th>job</th>
      <th>ANALYST</th>
      <th>CLERK</th>
      <th>MANAGER</th>
      <th>PRESIDENT</th>
      <th>SALESMAN</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>cnt</th>
      <td>2</td>
      <td>4</td>
      <td>3</td>
      <td>1</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.pivot_table(columns='deptno',aggfunc='sum')
x=x.iloc[[5],0:]
x.index=['sumsal']
x
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
      <th>deptno</th>
      <th>10</th>
      <th>20</th>
      <th>30</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>sumsal</th>
      <td>8750.0</td>
      <td>10875.0</td>
      <td>9400.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
x=emp.groupby('deptno')['sal'].sum().reset_index()
x.columns=['deptno','sumsal']
x.pivot_table(columns='deptno')
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
      <th>deptno</th>
      <th>10</th>
      <th>20</th>
      <th>30</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>sumsal</th>
      <td>8750</td>
      <td>10875</td>
      <td>9400</td>
    </tr>
  </tbody>
</table>
</div>




```python
emp['hire_year']=pd.to_datetime(emp['hiredate']).dt.year

x=emp.groupby('hire_year')['sal'].sum().reset_index()
x.pivot_table(columns='hire_year')

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
      <th>hire_year</th>
      <th>1980</th>
      <th>1981</th>
      <th>1982</th>
      <th>1983</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>sal</th>
      <td>800</td>
      <td>22825</td>
      <td>4300</td>
      <td>1100</td>
    </tr>
  </tbody>
</table>
</div>




```python
#직업 직업별 인원수를 그래프로 
import matplotlib.pyplot as plt
x=emp.pivot_table(columns = 'deptno',aggfunc='sum')
x2=x.iloc[[4],0:]
x2.plot.bar()
```




    <AxesSubplot:>




    
![png](output_15_1.png)
    



```python
import  pandas  as  pd
emp = pd.read_csv("c:\data\emp2.csv")
result = emp.groupby('deptno')['sal'].sum().reset_index()
result.plot.bar(x='deptno', color='red')

```




    <AxesSubplot:xlabel='deptno'>




    
![png](output_16_1.png)
    



```python
x=emp.pivot_table( index='job',columns ='deptno', values='sal', aggfunc='sum')
x.fillna(0,inplace=True)
x
#df.fillna(0,inplace=True) 결측치를 0으로 채워 넣어라 
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
      <th>deptno</th>
      <th>10</th>
      <th>20</th>
      <th>30</th>
    </tr>
    <tr>
      <th>job</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ANALYST</th>
      <td>0.0</td>
      <td>6000.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>CLERK</th>
      <td>1300.0</td>
      <td>1900.0</td>
      <td>950.0</td>
    </tr>
    <tr>
      <th>MANAGER</th>
      <td>2450.0</td>
      <td>2975.0</td>
      <td>2850.0</td>
    </tr>
    <tr>
      <th>PRESIDENT</th>
      <td>5000.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>SALESMAN</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>5600.0</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python

```
