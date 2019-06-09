---
title: "Creating Arrays"
author: "Muthu mani"
date: 2019-06-09
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np
```

# 1D array


```python
# 1D array
a = np.array([1, 2, 3])
a
```




    array([1, 2, 3])




```python
a.shape
```




    (3,)



# 2D array


```python
# 2D array
b = np.array([(1.5, 2, 3), (4, 5, 6)])
b
```




    array([[1.5, 2. , 3. ],
           [4. , 5. , 6. ]])




```python
b.shape
```




    (2, 3)



# 3D array


```python
c = np.array([
    [(1.5, 2, 3), (4, 5, 6)],
    [(3, 2, 1), (4, 5, 6)]
])
c
```




    array([[[1.5, 2. , 3. ],
            [4. , 5. , 6. ]],
    
           [[3. , 2. , 1. ],
            [4. , 5. , 6. ]]])




```python
c.shape
```




    (2, 2, 3)




```python

```
