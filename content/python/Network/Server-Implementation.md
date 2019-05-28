---
title: "Server Implementation"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false
---
* Network server are a bit more tricky
* must listen for incoming connections on a well-know port number
* Tyically run foreve in a server-loop
* May have to service multiple clients

# TCP Server


```python
from socket import *
s = socket(AF_INET, SOCK_STREAM)
s.bind(("127.0.0.1", 9000)) # binds the socket to a specific address
s.listen(5) #Tells operating system to start listening for connections on the socket

while True:
    clientsocket, address = s.accept() #Accept a new client connection
    # clientsocket - This is a new socket that's used for data
    # address - This is the network/port address of the client that connected
    print("connection from {address}")
    clientsocket.send(bytes("Hello {address[0]}", 'utf-8')) # send data to client to client socket
    # send data can be bytes
    clientsocket.close()
    
```

# client


```python
from socket import *
s = socket(AF_INET, SOCK_STREAM)
s.connect(("127.0.0.1", 9000)) # connecting to server by specifice addres and port

msg = s.recv(1024) # receive data and stord buffer, IN this case buffer size is 1024 character
print(msg.decode('utf-8'))

```


```python

```
