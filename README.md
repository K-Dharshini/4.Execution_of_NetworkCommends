# EXP4a. Simulating PING command

## Aim:
Use of Network commands in Real Time environment.

## Software : 
Command Prompt And Network Protocol Analyzer

## Procedure:
To do this EXPERIMENT- follows these steps:

In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also capture ping and traceroute PDUs using a network protocol analyzer 

All commands related to Network configuration which includes how to switch to privilege mode and normal mode and how to configure router interface and how to save this configuration to flash memory or permanent memory.

This commands includes

• Configuring the Router commands

• General Commands to configure network

• Privileged Mode commands of a router 

• Router Processes & Statistics

• IP Commands

• Other IP Commands e.g. show ip route etc.

## Program:
# Client
~~~
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname,verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
~~~

# Server
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
~~~

## Output:
# Client
![image](https://github.com/K-Dharshini/4.Execution_of_NetworkCommends/assets/139334830/f65f73fe-b33e-4b9e-92d8-f8a0bead45e6)

# Server
![image](https://github.com/K-Dharshini/4.Execution_of_NetworkCommends/assets/139334830/b93fc2af-4b1d-45ab-89c7-07d1535289b7)

## Result
Thus, the Execution of Network commands is performed.
