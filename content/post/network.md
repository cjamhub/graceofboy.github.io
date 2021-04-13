---
title: "Network"
date: 2021-04-13T10:51:25+08:00
archives: "2021"
tags: []
author: Jam
---
# NetWork

> original ：[Computer Network Tutorials - GeeksforGeeks](https://www.geeksforgeeks.org/computer-network-tutorials/)  

## Basic Concept
### Identifiers of network
- IP address
- MAC address
- Port
- Socket
- DNS Server
- ARP 
- RARP -> DHCP

### OSI
- Layer 7 : Application Layer
- Layer 6 : Presentation Layer
- Layer 5 : Session Layer
- Layer 4 : Transport Layer
- Layer 3 : Network Layer
- Layer 2 : Data Link Layer (DLL)
- Layer 1 : Physical Layer

### Protocol
- IP : Internet Protocol
- FTP : File Transfer Protocol
- SMTP : Simple Mail Transfer Protocol
- HTTP : Hyper Text Transfer Protocol

### Network Types
- LANs : Local Area Networks
- MANs : Metropolitan Area Networks
- WANs : Wide Area Networks

## TCP/IP : Transmission Control Protocol/Internet Protocol
The TCP/IP model is a concise version of the OSI model.

### Layers
- Application Layer/Process
- Transport Layer/Host-to-Host
- Internet Layer
- Network Access Layer/Link Layer

#### Network Access Layer
This layer corresponds to the combination of Data Link Layer and Physical Layer of the OSI model.

#### Internet Layer
This layer parallels the functions of OSI’s Network layer. It defines the protocols which are responsible for logical transmission of data over the entire network. The main protocols residing at this layer are :
	
    1. IP : stands for Internet Protocol and it is responsible for delivering packets from the source host to the destination host by looking at the IP addresses in the packet headers. 
	2. ICMP : stands for Internet Control Message Protocol. It is encapsulated within IP datagrams and is responsible for providing hosts with information about network problems.
	3. ARP : stands for Address Resolution Protocol. Its job is to find the hardware address of a host from a known IP address. ARP has several types: Reverse ARP, Proxy ARP, Gratuitous ARP and Inverse ARP.

#### Transport Layer
It is responsible for end-to-end communication and error-free delivery of data.  The two main protocols present in this layer are :

	1. Transmission Control Protocol (TCP): It is known to provide reliable and error-free communication between end systems. It performs sequencing and segmentation of data.
	2. User Datagram Protocol (UDP): UDP is connectionless.

#### Application Layer
 It is responsible for node-to-node communication and controls user-interface specifications. Some of the protocols present in this layer are: HTTP, HTTPS, FTP, TFTP, Telnet, SSH, SMTP, SNMP, NTP, DNS, DHCP, NFS, X Window, LPD. The main protocols residing at this layer are : 

	1. HTTP and HTTPS: HTTP stands for Hypertext transfer protocol. It is used by the World Wide Web to manage communications between web browsers and servers. HTTPS stands for HTTP-Secure. It is a combination of HTTP with SSL(Secure Socket Layer). It is efficient in cases where the browser need to fill out forms, sign in, authenticate and carry out bank transactions.
	2. SSH : SSH stands for Secure Shell. It is a terminal emulations software similar to Telnet. The reason SSH is more preferred is because of its ability to maintain the encrypted connection. It sets up a secure session over a TCP/IP connection.
	3. NTP : NTP stands for Network Time Protocol. It is used to synchronize the clocks on our computer to one standard time source. It is very useful in situations like bank transactions. 


