---
title: "Using Array And Scalars"
author: "muth mani"
date: 2019-06-12
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np
```


```python
# creating an array
arr1 = np.array([(1, 2, 3, 4), (8, 9, 10, 11)])
arr1
```




    array([[ 1,  2,  3,  4],
           [ 8,  9, 10, 11]])




```python
# multiplication
arr1 * arr1
```




    array([[  1,   4,   9,  16],
           [ 64,  81, 100, 121]])




```python
# substraction
arr1 - arr1
```




    array([[0, 0, 0, 0],
           [0, 0, 0, 0]])




```python
# division
1 / arr1
```




    array([[1.        , 0.5       , 0.33333333, 0.25      ],
           [0.125     , 0.11111111, 0.1       , 0.09090909]])




```python
# power
arr1 ** 3
```




    array([[   1,    8,   27,   64],
           [ 512,  729, 1000, 1331]])




```python

```
