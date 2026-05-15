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
s.connect(('localhost', 8000))

n = int(input("Enter number of frames: "))

for i in range(n):
    msg = input("Enter frame: ")
    s.send(msg.encode())

    ack = s.recv(1024).decode()
    print("Received:", ack)

s.close()
```
## OUTPUT
## Server side
<img width="1838" height="265" alt="Screenshot 2026-05-15 092812" src="https://github.com/user-attachments/assets/a7d66890-e6ba-409b-b97b-55e92fed8a99" />

## Client side
<img width="1817" height="344" alt="Screenshot 2026-05-15 092915" src="https://github.com/user-attachments/assets/41bd7b80-369b-41a5-999c-c31c7453b47c" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
