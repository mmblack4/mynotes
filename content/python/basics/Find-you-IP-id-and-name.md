---
title: "Find My IP-id and name"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false
---

```python
import socket
```


```python
hostname = socket.gethostname()
ipaddr = socket.gethostbyname(hostname)
```


```python
print('your computer name:',hostname)
print('your computer IP:',ipaddr)
```

    your computer name: mmblack
    your computer IP: 127.0.1.1



```python

```
