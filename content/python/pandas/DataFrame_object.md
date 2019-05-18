---
title: "DataFrame object"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false
---The pandas DataFrame object
    a pandas series represents a single array of values, with an index label for each value.if you want to have more than one series of data that is aligned by a common index, then a Pandas DataFrame is used.

```python
import pandas as pd
from pandas import DataFrame, Series
```


```python
dates = pd.date_range('2019-05-18', '2019-05-25')
temp_chennai = Series([36, 37, 36, 37, 37, 37, 37, 37],
                     index = dates)
temp_delhi = Series([34, 39, 41, 41, 41, 41, 41, 42],
                   index = dates)
```


```python
# create a DataFrame from the two Series objects temp_chennai and temp_delhi
# and give them column names
temps_df = DataFrame({
    "chennai" : temp_chennai,
     "Delhi" : temp_delhi
}) 
temps_df
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
      <th>chennai</th>
      <th>Delhi</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2019-05-18</th>
      <td>36</td>
      <td>34</td>
    </tr>
    <tr>
      <th>2019-05-19</th>
      <td>37</td>
      <td>39</td>
    </tr>
    <tr>
      <th>2019-05-20</th>
      <td>36</td>
      <td>41</td>
    </tr>
    <tr>
      <th>2019-05-21</th>
      <td>37</td>
      <td>41</td>
    </tr>
    <tr>
      <th>2019-05-22</th>
      <td>37</td>
      <td>41</td>
    </tr>
    <tr>
      <th>2019-05-23</th>
      <td>37</td>
      <td>41</td>
    </tr>
    <tr>
      <th>2019-05-24</th>
      <td>37</td>
      <td>41</td>
    </tr>
    <tr>
      <th>2019-05-25</th>
      <td>37</td>
      <td>42</td>
    </tr>
  </tbody>
</table>
</div>




```python
temps_df['chennai'] # get the column with the name chennai
```




    2019-05-18    36
    2019-05-19    37
    2019-05-20    36
    2019-05-21    37
    2019-05-22    37
    2019-05-23    37
    2019-05-24    37
    2019-05-25    37
    Freq: D, Name: chennai, dtype: int64




```python
temps_df['Delhi'] # get the column with the name Delhi
```




    2019-05-18    34
    2019-05-19    39
    2019-05-20    41
    2019-05-21    41
    2019-05-22    41
    2019-05-23    41
    2019-05-24    41
    2019-05-25    42
    Freq: D, Name: Delhi, dtype: int64




```python
temps_df.chennai # gretrieve the chennai column through property syntax
```




    2019-05-18    36
    2019-05-19    37
    2019-05-20    36
    2019-05-21    37
    2019-05-22    37
    2019-05-23    37
    2019-05-24    37
    2019-05-25    37
    Freq: D, Name: chennai, dtype: int64




```python
temp_diffs = abs(temps_df.chennai - temps_df.Delhi)
temps_df['Difference'] = temp_diffs
temps_df
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
      <th>chennai</th>
      <th>Delhi</th>
      <th>Difference</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2019-05-18</th>
      <td>36</td>
      <td>34</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2019-05-19</th>
      <td>37</td>
      <td>39</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2019-05-20</th>
      <td>36</td>
      <td>41</td>
      <td>5</td>
    </tr>
    <tr>
      <th>2019-05-21</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-22</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-23</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-24</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-25</th>
      <td>37</td>
      <td>42</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
temps_df.columns # get columns 
```




    Index(['chennai', 'Delhi', 'Difference'], dtype='object')




```python
temps_df.Difference[1:4]
```




    2019-05-19    2
    2019-05-20    5
    2019-05-21    4
    Freq: D, Name: Difference, dtype: int64




```python
temps_df.iloc[0] # get the row array postition 0
```




    chennai       36
    Delhi         34
    Difference     2
    Name: 2019-05-18 00:00:00, dtype: int64




```python
temps_df.ix[1].index
```

    /home/mmblack/anaconda3/lib/python3.7/site-packages/ipykernel_launcher.py:1: DeprecationWarning: 
    .ix is deprecated. Please use
    .loc for label based indexing or
    .iloc for positional indexing
    
    See the documentation here:
    http://pandas.pydata.org/pandas-docs/stable/indexing.html#ix-indexer-is-deprecated
      """Entry point for launching an IPython kernel.





    Index(['chennai', 'Delhi', 'Difference'], dtype='object')




```python
temps_df.loc['2019-05-19']
```




    chennai       37
    Delhi         39
    Difference     2
    Name: 2019-05-19 00:00:00, dtype: int64




```python
temps_df.iloc[[1, 3, 5]] # select only rows 1, 3, 5
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
      <th>chennai</th>
      <th>Delhi</th>
      <th>Difference</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2019-05-19</th>
      <td>37</td>
      <td>39</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2019-05-21</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-23</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
temps_df.Delhi >40 # which values in Delhi column are great then 40
```




    2019-05-18    False
    2019-05-19    False
    2019-05-20     True
    2019-05-21     True
    2019-05-22     True
    2019-05-23     True
    2019-05-24     True
    2019-05-25     True
    Freq: D, Name: Delhi, dtype: bool




```python
temps_df[temps_df.Delhi > 40] # return the rows where the temps for delhi great then 40
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
      <th>chennai</th>
      <th>Delhi</th>
      <th>Difference</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2019-05-20</th>
      <td>36</td>
      <td>41</td>
      <td>5</td>
    </tr>
    <tr>
      <th>2019-05-21</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-22</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-23</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-24</th>
      <td>37</td>
      <td>41</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2019-05-25</th>
      <td>37</td>
      <td>42</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
