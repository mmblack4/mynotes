---
title: "break with youtube song"
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
song_list =[
    "https://www.youtube.com/watch?v=kJQP7kiw5Fk",
    "https://www.youtube.com/watch?v=euCqAq6BRa4",
    "https://www.youtube.com/watch?v=UtF6Jej8yb4",
    "https://www.youtube.com/watch?v=nYh-n7EOtMA",
    "https://www.youtube.com/watch?v=J1OsKJW51HY",
]
```


```python
def break_timer(interval):
    for i in song_list:
        time.sleep(interval)
        print('time to take brake')
        webbrowser.open(i)
    
```


```python
break_timer(5)
```

    time to take brake
    time to take brake
    time to take brake



```python

```
