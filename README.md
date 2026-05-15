# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## Server.py
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for connection...")
conn, addr = s.accept()
print("Connected to", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print("Frame received:", data)
    conn.send("ACK".encode())

conn.close()
```
## Client.py
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for connection...")
conn, addr = s.accept()
print("Connected to", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print("Frame received:", data)
    conn.send("ACK".encode())

conn.close()
```
## OUTPUT
## Server side
<img width="1838" height="265" alt="image" src="https://github.com/user-attachments/assets/cd01c53a-79f7-492c-a6d5-da528460c6a7" />
## Client side
<img width="1817" height="344" alt="image" src="https://github.com/user-attachments/assets/855ad5f7-877b-43ba-8ff7-6bd26e947a21" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
