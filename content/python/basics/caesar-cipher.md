---
title: "caesar cipher"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false
---Caesar Cipher:
    The Caesar cipher is one of the earliest known and simplest ciphers. 
    It is a type of substitution cipher in which each letter in the plaintext is 'shifted' 
    a certain number of places down the alphabet. For example, with a shift of 1, A would be replaced by B,
    B would become C, and so on. The method is named after Julius Caesar, who apparently used it to communicate with
    his generals.


```python
alphabet = ' abcdefghijklmnopqrstuvwxyz '
```


```python
def encoder(mgs,key):
    sour = ''
    for i in mgs:
        sour+=alphabet[alphabet.find(i)+key]
    return sour
```


```python
def decoder(mgs,key):
    sour = ''
    for i in mgs:
        sour+=alphabet[alphabet.find(i)-key]
    return sour
```


```python
print(encoder('hello my name is caesar',1))
```

    ifmmpanzaobnfajtadbftbs



```python
print(decoder('ifmmpanzaobnfajtadbftbs',1))
```

    hello my name is caesar



```python

```
