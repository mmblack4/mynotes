---
title: "Indexing Arrays"
author: "muth mani"
date: 2019-06-12
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np
```

# creating array range 0 to 11



```python
arr = np.arange(0, 11)
arr
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10])



# array index of 8


```python
arr[8]
```




    8



# get by range 1 to 5


```python
arr[1:5]
```




    array([1, 2, 3, 4])




```python
arr[0:5]
```




    array([0, 1, 2, 3, 4])



# set value for range



```python
arr[0:5] = 100
```


```python
arr
```




    array([100, 100, 100, 100, 100,   5,   6,   7,   8,   9,  10])




```python
#
slice_of_arr = arr[0:5]
```


```python
slice_of_arr
```




    array([100, 100, 100, 100, 100])



# Index 2D array


```python
arr2d = np.array(((1, 2 ,3), (4, 5, 6), (19, 30, 20)))
arr2d
```




    array([[ 1,  2,  3],
           [ 4,  5,  6],
           [19, 30, 20]])



# Row index


```python
arr2d[0]
```




    array([1, 2, 3])




```python
arr2d[0][0]
```




    1



 # 2D Slice


```python
arr2d
```




    array([[ 1,  2,  3],
           [ 4,  5,  6],
           [19, 30, 20]])




```python
arr2d[:3,1:]
```




    array([[ 2,  3],
           [ 5,  6],
           [30, 20]])



# Fancy Index


```python
# we can put index value in any order
arr2d[[2,1]]
```




    array([[19, 30, 20],
           [ 4,  5,  6]])




```python

```
