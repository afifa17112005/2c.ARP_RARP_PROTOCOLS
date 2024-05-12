# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
Name:A.Afifa Reg.no:212223040008
## PROGRAM - ARP
## client:
```import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; while True:
ip=c.recv(1024).decode()
try:
c.send(address[ip].encode())
except KeyError:
c.send("Not Found".encode())
```
## server :
```import socket
s = socket.socket()
s.connect(('localhost',8000))
while True:
ip = input("Enter logical address: ")
s.send(ip.encode())
print("MAC Address",s.recv(1024).decode())
```
## OUPUT - ARP
## client :
![320836752-f29e2182-0d63-40e0-b953-0e7ec5749fca](https://github.com/afifa17112005/2c.ARP_RARP_PROTOCOLS/assets/147080931/c9c668cb-d390-4531-82e8-67b295048f4f)
## server :
![320836871-57768d61-b90b-4fa1-8709-ae97ecdc6e3b](https://github.com/afifa17112005/2c.ARP_RARP_PROTOCOLS/assets/147080931/04807d7b-6188-4cbb-a151-126870e4d272)


## PROGRAM - RARP
## client :
```import socket
s = socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr = s.accept()
address = {"6A:08:AA:C2":"165.165.80.1","8A:BC:E3:FA":"165.165.79.1"}
while True:
ip = c.recv(1024).decode()
try:
c.send(address[ip].encode())
except KeyError:
c.send("Not Found".encode())
```
## server:
```import socket
s = socket.socket()
s.connect(('localhost',8000))
while True:
ip = input("Enter MAC address: ")
s.send(ip.encode())
print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP:
## client:
![320838357-84b84a2b-9049-4d38-b8c4-4b518287dee3](https://github.com/afifa17112005/2c.ARP_RARP_PROTOCOLS/assets/147080931/50add173-0141-43bd-b130-c30f1e9d6043)
## server :
![320839199-1fb76e5a-b398-4253-8147-990588ced9c4](https://github.com/afifa17112005/2c.ARP_RARP_PROTOCOLS/assets/147080931/0c74f757-1f12-4d76-8b57-c3f60edd4d76)


## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
