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
## SERVER-
```
import socket

# Create socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind to localhost and port
server_socket.bind(('127.0.0.1', 12345))

# Listen for connection
server_socket.listen(1)
print("Server is waiting for connection...")

conn, addr = server_socket.accept()
print("Connected to:", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break
    print("Client:", data)
    conn.send(data.encode())  # Echo back

conn.close()
server_socket.close()
```
## CLIENT -
```
import socket

# Create socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to server
client_socket.connect(('127.0.0.1', 12345))

while True:
    msg = input("Enter message: ")
    client_socket.send(msg.encode())

    data = client_socket.recv(1024).decode()
    print("Server echoed:", data)

    if msg.lower() == "exit":
        break

client_socket.close()
```

## OUPUT
## SERVER-CLIENT-
<img width="1313" height="277" alt="image" src="https://github.com/user-attachments/assets/7e731c4f-bc9f-40af-82cd-37f253282fb6" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
