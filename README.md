# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
server.py
```
import socket

s = socket.socket()
s.bind(('localhost', 12345))
s.listen(1)

print("Waiting for client...")
c, addr = s.accept()
print("Client connected")

while True:
    msg = c.recv(1024).decode()
    print("Client:", msg)

    if msg == "exit":
        break

    reply = input("Server: ")
    c.send(reply.encode())

    if reply == "exit":
        break

c.close()
s.close()

```
client.py
```
import socket

s = socket.socket()
s.connect(('localhost', 12345))

while True:
    msg = input("Client: ")
    s.send(msg.encode())

    if msg == "exit":
        break

    reply = s.recv(1024).decode()
    print("Server:", reply)

    if reply == "exit":
        break

s.close()

```

## OUPUT
<img width="585" height="165" alt="image" src="https://github.com/user-attachments/assets/0bd4d0a9-50d9-40b4-9bb6-82be2112c5dd" />
<img width="587" height="141" alt="image" src="https://github.com/user-attachments/assets/c098d3ec-d53d-4dd4-a5f7-0f16e2cb408d" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
