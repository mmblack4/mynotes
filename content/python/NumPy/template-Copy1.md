---
title: "numpy array and basic array operation"
author: "TACT"
date: 2019-05-06
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np

```


```python
# array is use to creat a numpy array
a1 = np.array([1, 2, 3, 4, 5])
a1
```




    array([1, 2, 3, 4, 5])




```python
# type
type(a1)
```




    numpy.ndarray




```python
# how many elements
np.size(a1)
```




    5




```python
# any float in the sequences makes 
# it an array of floats
a2 = np.array([1, 2, 3, 4, 5.0])
a2
```




    array([1., 2., 3., 4., 5.])




```python
# array is all of one type
a2.dtype
```




    dtype('float64')




```python
# shorthand to repeat a sequence 10 times
a3 = np.array([0]*10)
a3
```




    array([0, 0, 0, 0, 0, 0, 0, 0, 0, 0])




```python
# convert a python range to numpy array
np.array(range(10))
```




    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
# create a numpy array of 10 0.0's
np.zeros(10)
```




    array([0., 0., 0., 0., 0., 0., 0., 0., 0., 0.])




```python
# force it to be of int instead of float64
np.zeros(10, dtype=int)
```




    array([0, 0, 0, 0, 0, 0, 0, 0, 0, 0])




```python
# make "a range" starting at 0 and with 10 values
np.arange(0, 10)
```




    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
# 0<= x < 10 increment by two
np.arange(0, 10 ,2)
```




    array([0, 2, 4, 6, 8])




```python
# 10 >= x > 0, counting down
np.arange(10, 0, -1)
```




    array([10,  9,  8,  7,  6,  5,  4,  3,  2,  1])




```python

```
