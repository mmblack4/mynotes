---
title: "Inspecting Your Array"
author: "muth mani"
date: 2019-06-09
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np
```


```python
# sample array
data = np.full((3, 4), 4)
data
```




    array([[4, 4, 4, 4],
           [4, 4, 4, 4],
           [4, 4, 4, 4]])



# Array dimensions


```python
data.shape #3x4
```




    (3, 4)



# Length of array




```python
len(data) # 3 row
```




    3



# Number of array dimensions


```python
data.ndim # 2D array
```




    2



# Number of array elements


```python
data.size # 3x4 = 12
```




    12



# Data type of array elements


```python
data.dtype # return object
```




    dtype('int64')



# Name of data type


```python
data.dtype.name # return string
```




    'int64'



# Convert an array to different type


```python
data = data.astype(float)
data
```




    array([[4., 4., 4., 4.],
           [4., 4., 4., 4.],
           [4., 4., 4., 4.]])




```python
data.dtype
```




    dtype('float64')




```python

```
