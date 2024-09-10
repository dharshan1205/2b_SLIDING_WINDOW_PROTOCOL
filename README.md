# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
NAME: INFANCIA FELCY P
REG NO: 212223040067

## AIM:
To write a python program for Implementation of sliding Window Protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
SERVER:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
CLINET
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
SERVER:
![Screenshot 2024-09-10 085118](https://github.com/user-attachments/assets/fe9583b0-1a32-47f8-86ee-23d543cb7fd6)

CLINET:
![Screenshot 2024-09-10 085352](https://github.com/user-attachments/assets/5821e61a-46c2-46f6-9809-98dc067a75f7)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
