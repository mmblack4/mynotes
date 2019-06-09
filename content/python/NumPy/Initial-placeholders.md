---
title: "Initial Placeholders"
author: "muthu mani"
date: 2019-06-09
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np
```

# Create an array of Zeros


```python
np.zeros((3,4)) # 3x4
```




    array([[0., 0., 0., 0.],
           [0., 0., 0., 0.],
           [0., 0., 0., 0.]])



# Create an array of ones


```python
np.ones((2,3,4),dtype=np.int16) #2x3x4
```




    array([[[1, 1, 1, 1],
            [1, 1, 1, 1],
            [1, 1, 1, 1]],
    
           [[1, 1, 1, 1],
            [1, 1, 1, 1],
            [1, 1, 1, 1]]], dtype=int16)



# Create an array of evenly


```python
# array range 10 to 25
np.arange(10,25) 
```




    array([10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24])




```python
# array range 10 to 25 incremant by 5
np.arange(10,25,5)
```




    array([10, 15, 20])



# Spaced values


```python
np.linspace(0, 2, 9)
```




    array([0.  , 0.25, 0.5 , 0.75, 1.  , 1.25, 1.5 , 1.75, 2.  ])



# Create a constant array


```python
# array of 2X2 value of 4
np.full((2, 2), 4)
```




    array([[4, 4],
           [4, 4]])



# Create a identity matrix


```python
# Identity matrix of 2X2
np.eye(2)
```




    array([[1., 0.],
           [0., 1.]])



# Create an array with random values


```python
# 2x2 matrix of random values
np.random.random((2,2))
```




    array([[0.4825663 , 0.8771236 ],
           [0.1197411 , 0.07159758]])



# Create an empty array


```python
# 3x2 matrix of empty values
np.empty((3, 2))
```




    array([[4.64407429e-310, 0.00000000e+000],
           [0.00000000e+000, 0.00000000e+000],
           [0.00000000e+000, 0.00000000e+000]])




```python

```
