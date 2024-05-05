# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
### SERVER:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)

```
### CLIENT:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))

```
## OUPUT
### SERVER:
![310513763-21e8cf8f-c448-445a-a520-02462699f482](https://github.com/Sabariakash22009103/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/119390227/c0240e47-00bc-4cad-bd6c-ba03ea774c51)
### CLIENT:
![310513915-4f0dca11-0077-463c-80d3-eaf1922c1ac4](https://github.com/Sabariakash22009103/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/119390227/8f9d243b-6222-4dd4-9e9d-ce9441d8c101)
## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
