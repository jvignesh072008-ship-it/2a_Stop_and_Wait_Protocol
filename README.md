# 2a Stop and Wait Protocol
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
### Server:
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    data = s.recv(1024).decode()
    if not data:
        break
    print(data)
    s.send("Acknowledgement Recived".encode())
```
### Client:
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
## OUTPUT
<img width="1920" height="1080" alt="Screenshot 2026-05-20 130834" src="https://github.com/user-attachments/assets/4256d78a-c561-425b-b4d4-5373d2b523b5" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
