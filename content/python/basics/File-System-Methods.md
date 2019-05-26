---
title: "File System Methods"
author: "TACT"
date: 2019-05-25
description: "-"
type: technical_note
draft: false
---

```python
import os
```
Get Info

```python
# get the current working directory path as a string (pwd - linux, windows)
os.getcwd() 
```




    '/home/mmblack/Documents/project/mynotes/content/python/basics'




```python
# get the contents of the current working directory as a list of strings(ls -linux, dir - windows)
os.listdir()
```




    ['simple-python.md',
     'rock-paper-scissor.md',
     'Find-you-IP-id-and-name.ipynb',
     'auto-search.ipynb',
     'template-simple-add.md',
     'auto-search.md',
     'break-with-youtube-song.ipynb',
     'caesar-cipher.md',
     'template-simple-add.ipynb',
     'template-Copy1.md',
     'mult.md',
     'Find-you-IP-id-and-name.md',
     '.ipynb_checkpoints',
     'simple-python.ipynb',
     'template.ipynb',
     'template.md',
     'caesar-cipher.ipynb',
     'mult.ipynb',
     'File-System-Methods.ipynb',
     'break-with-youtube-song.md',
     'rock-paper-scissor.ipynb']




```python
# returns a generator with name and path info for directories and 
# files in the the current directory and all subdirectories— no exact short CLI equivalent, 
# but ls -R provides subdirectory names and the names of files within subdirectories

path = '/home/mmblack/Documents/project/mynotes/content/'
for root, dirs, files in os.walk(path):
    print(root)
    print(dirs)
    print(files)
    print('______________________________________________________________')
```

    /home/mmblack/Documents/project/mynotes/content/
    ['python']
    []
    ______________________________________________________________
    /home/mmblack/Documents/project/mynotes/content/python
    ['basics', 'pandas']
    []
    ______________________________________________________________
    /home/mmblack/Documents/project/mynotes/content/python/basics
    ['.ipynb_checkpoints']
    ['simple-python.md', 'rock-paper-scissor.md', 'Find-you-IP-id-and-name.ipynb', 'auto-search.ipynb', 'template-simple-add.md', 'auto-search.md', 'break-with-youtube-song.ipynb', 'caesar-cipher.md', 'template-simple-add.ipynb', 'template-Copy1.md', 'mult.md', 'Find-you-IP-id-and-name.md', 'simple-python.ipynb', 'template.ipynb', 'template.md', 'caesar-cipher.ipynb', 'mult.ipynb', 'File-System-Methods.ipynb', 'break-with-youtube-song.md', 'rock-paper-scissor.ipynb']
    ______________________________________________________________
    /home/mmblack/Documents/project/mynotes/content/python/basics/.ipynb_checkpoints
    []
    ['mult-checkpoint.ipynb', 'caesar-cipher-checkpoint.ipynb', 'rock-paper-scissor-checkpoint.ipynb', 'File-System-Methods-checkpoint.ipynb', 'auto-search-checkpoint.ipynb', 'Find-you-IP-id-and-name-checkpoint.ipynb', 'template-checkpoint.ipynb', 'break-with-youtube-song-checkpoint.ipynb', 'template-simple-add-checkpoint.ipynb']
    ______________________________________________________________
    /home/mmblack/Documents/project/mynotes/content/python/pandas
    ['.ipynb_checkpoints']
    ['DataFrame_object.md', 'Series_object.md', 'Series_object.ipynb', 'template-Copy2.ipynb', 'Loading_data_from_files.ipynb', 'zero.ipynb', 'DataFrame_object.ipynb', 'zero.md', 'Loading_data_from_files.md', 'template.ipynb', 'template.md', 'template-Copy2.md']
    ______________________________________________________________
    /home/mmblack/Documents/project/mynotes/content/python/pandas/.ipynb_checkpoints
    []
    ['zero-checkpoint.ipynb', 'DataFrame_object-checkpoint.ipynb', 'Series_object-checkpoint.ipynb', 'template-checkpoint.ipynb', 'template-Copy2-checkpoint.ipynb', 'Loading_data_from_files-checkpoint.ipynb']
    ______________________________________________________________

Change Things

```python
#change the current working directory (cd -linux,windows)

print("curent dir:",os.getcwd())
os.chdir('/')
print("new dir:",os.getcwd())
```

    curent dir: /home/mmblack/Documents/project/mynotes/content/python/basics
    new dir: /



```python
# create a path for later use
os.path.join()
```


```python
# make directory(aka folder) (mkdir -linux)
os.makedirs('/home/mmblack/Disktop/happy')
# change directory
os.chdir('/home/mmblack/Disktop')
# list directory 
os.listdir()
```




    ['happy']




```python
# copy a file or directory (cp -linux)
# shutil.copy2("source_file", "destination")
import shutil #this library of copy

```
