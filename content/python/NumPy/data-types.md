---
title: "Data Types"
author: "Muthu mani"
date: 2019-06-09
description: "-"
type: technical_note
draft: false
---

```python
import numpy as np
```

# Signed 64-bit integer types


```python
np.int64
```




    int




```python
np.full((3, 3), 4.001, dtype=np.int64)
```




    array([[4, 4, 4],
           [4, 4, 4],
           [4, 4, 4]])



# Standard double-precision floating point


```python
np.float32
```




    numpy.float32




```python
np.full((3, 3), 4.032, dtype=np.float32)
```




    array([[4.032, 4.032, 4.032],
           [4.032, 4.032, 4.032],
           [4.032, 4.032, 4.032]], dtype=float32)



# Compllex numbers represented by 128 floats


```python
np.complex
```




    complex



# Boolean type storing TRUE and FALSE values


```python
np.bool
```




    bool




```python
np.eye(3, dtype=np.bool)
```




    array([[ True, False, False],
           [False,  True, False],
           [False, False,  True]])


