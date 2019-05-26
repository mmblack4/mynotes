---
title: "Series Object"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false
---

```python
The pandas series object
    the base data structure of pandas is the sereis object,which is 
    designed to operate similar to a numpy array but also add index         capablilities 
```


```python
import pandas as pd
from pandas import Series
```


```python
s = Series([1, 2, 3, 4]) #create a four item
s
```


```python
s[[1, 3]] #return a series with the rows with labels 1 and 3
```




    1    2
    3    4
    dtype: int64




```python
s = Series([1, 2, 3, 4],
          index = ['a', 'b', 'c', 'd']) #create a item with index
s
```




    a    1
    b    2
    c    3
    d    4
    dtype: int64




```python
s[['a', 'd']]
```




    a    1
    d    4
    dtype: int64




```python
s.index #it will show index

```




    Index(['a', 'b', 'c', 'd'], dtype='object')




```python
s.values #it will show values
```




    array([1, 2, 3, 4])




```python
dates = pd.date_range('2019-05-18', '2019-05-25')
dates
```




    DatetimeIndex(['2019-05-18', '2019-05-19', '2019-05-20', '2019-05-21',
                   '2019-05-22', '2019-05-23', '2019-05-24', '2019-05-25'],
                  dtype='datetime64[ns]', freq='D')




```python
temp_chennai = Series([36, 37, 36, 37, 37, 37, 37, 37],
                     index = dates)
```


```python
temp_delhi = Series([34, 39, 41, 41, 41, 41, 41, 42],
                   index = dates)
```


```python
temp_chennai.mean()
```




    36.75




```python
temp_delhi.mean()
```




    40.0




```python
temp_diffs_between_chennai_and_delhi = abs(temp_delhi - temp_chennai)
temp_diffs_between_chennai_and_delhi
```




    2019-05-18    2
    2019-05-19    2
    2019-05-20    5
    2019-05-21    4
    2019-05-22    4
    2019-05-23    4
    2019-05-24    4
    2019-05-25    5
    Freq: D, dtype: int64




```python
temp_diffs_between_chennai_and_delhi['2019-05-20']
```




    5




```python

```
