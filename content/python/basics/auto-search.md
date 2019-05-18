---
title: "auto search"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false
---

```python
import webbrowser
import time
```


```python
search_topic = [
    "python basics",
    "python interview questions",
    "top analyze api",
    "how to create api in flask"
]
```


```python
def search():
    for topic in search_topic:
        webbrowser.open_new_tab('http://www.google.com/search?btnG=1&q=%s' %topic)
        time.sleep(2)
```


```python
search()
```


```python

```
