---
title: "rock paper scissor"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false
---

```python
import random
chose = ["rock","paper","scissor"]
```


```python
def play(youChose):
    computerChose = random.choice(chose)
    print('you:',youChose,',computer:',computerChose)
    if youChose == computerChose:
        return 'Draw'
    elif youChose == 'rock' and computerChose == 'paper':
        return "computer won"
    elif youChose == 'rock' and computerChose == 'scissor':
        return "you won"
    elif youChose == 'paper' and computerChose == 'rock':
        return 'you won'
    elif youChose == 'paper' and computerChose == 'scissor':
        return 'computer won'
    elif youChose == 'scissor' and computerChose == 'rock':
        return 'computer won'
    elif youChose == 'scissor' and computerChose == 'paper':
        return 'you won'
```


```python
play('rock')
```

    you: rock ,computer: paper





    'computer won'




```python
play('paper')
```

    you: paper ,computer: scissor





    'computer won'




```python
play('scissor')
```

    you: scissor ,computer: paper





    'you won'




```python
play('scissor')
```

    you: scissor ,computer: paper





    'you won'




```python
play('rock')
```

    you: rock ,computer: scissor





    'you won'




```python
play('rock')
```

    you: rock ,computer: rock





    'Draw'




```python

```
