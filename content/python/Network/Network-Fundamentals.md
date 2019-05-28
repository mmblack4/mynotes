---
title: "Network Fundamentals"
author: "TACT"
date: 2019-04-20
description: "-"
type: technical_note
draft: false
---
## The Problem

    * Communication between computers
    
    * It's just sending/receiving bits

## Two Min Issues

    * Addressing
    
        * Specifying a remote computer and service
        
    * Data transport
    
        * Moving bits back and forth

## Network Addressing

    * Machines have a hostname and IP address
    
    * Programs/services have port number

## Standard Ports

    * Ports for common services are Pressigned
    
         21  FTP
         
         22  SSH
         
         23  Telnet
         
         25  SMTP  (Mail)
         
         80  HTTP  (Web)
         
        110  POP3  (Mail)
        
        119  NNTP  (News)
        
        443  HTTPs (web)
        
    * Other port numbers may just be randomly assigned to programs by the operation system

## Using netstart

    * Use 'netstart' to view active network connections
    
        sheel: newstart -a
        
    * Note: Must execute from the command shell on both Unix and Windows

## Connections

    * Each endpoint of network connection is always represented by a host and post #
    
    * In python you write it out as a tuple (host, post)

## Client/Server concept
    * Each endpoint is a running program
    
    * servers wait for incoming connections and provide a service (e.g: web, mail)
    
    * Clients make connections to servers

## Request/Response Cycle
    * Most nerwork programs use a request/response model based on messages
    
    * Client sends a request message (eg: HTTP)
            GET /index.html HTTP/1.0
        
    * server sends back a response message
        HTTP/1.0 200 ok
        content-type: text/html
        content-length: 48823
        
        <html>
        .....
        
    * The exact fromat depends on the appllication

## Using Telnet
    * As a debugging aid, telnet can be used to directly communicate with manu services
        telnet hostnmae portnum
   

## Data Transport
    * There are two basic types of communication
    
    * Streams (TCP): computers establish a connection with each other and read/Write data in a continuous stream of byetes like a flie. This is the most common
    
    * Datagrams (UDP): Computers send discrete packets (or messages) to each other. Each packet contains a collection of bytes, but each packet is separate and self-contained.

## Sockets
    * Programming abstraction for network code
    
    * Socket: A communication endpoint
    
    * Supported by socket library module
    
    * Allows connections to be made and data to be transmitted in either direction

## Socket Basics
    * To create a socket
        import socket
        s = socket.socket(addr_family, type)
        
    * Address families
        socket.AF_INET  internet protocol (IPv4)
        socket.AF_INET6 internet protocol (IPV6)
        
    * Socket types
        socket.SOCK_STREAM connection baseed stream (TCP)
        socket.SOCK_DGRAM  Datagrams (UDP)
    

## socket Types
    * Almost all code will use one of following
    
        from socket import *
        
        s = socket(AF_INET, SOCK_STREAM)
        s = scoket(AF_INET, SOCK_DGRAM)
    
    * Most common case: TCP connection
        s = socket(AF_INET, SOCK_STREAM)
        

## Using a Scoket
    * creating a socket is onlu th first step
    
        s = socket(AF_INET, SOCK_STREAM)
        
    * Further use depends on application
    
    * Server
        * Listen for incoming connections
    
    * Client
        
        * Make an outgoing connection
    

# TCP Client
    * How to make an outgoing connection
        
        from socket import *
        s = socket(AF_INET, SOCK_STREAM)
        s.connect(('www.python.org', 80))
        s.send("GET /index.html HTTP/1.0\n\n")
        data = s.recv(10000)
        s.close()
        
    * s.connect(addr) makes a connection
        s.connect(('www.python.org',80))
       
    * Once connected, usd send(),recv() to transmit and receive data
    
    * close() shuts down the connection


```python

```
