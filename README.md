# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
To write a python program to Implement Sliding window protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
Developed by: ABDULRAWOOF

REG NO 212224230003
~~~
 Client:
 import socket
 s=socket.socket()
 s.bind(('localhost',8000))
 s.listen(5)
 c,addr=s.accept()
 size=int(input("Enter number of frames to send : "))
 l=list(range(size))
 s=int(input("enter window size : "))
 st= 0
 i=0
 while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
~~~
~~~
Server :
 import socket
 s=socket.socket()
 s.connect(('localhost',8000))
 while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived".encode())
~~~
## OUPUT
## Client

![WhatsApp Image 2025-03-27 at 11 36 22_53a0ea5d CLIENT](https://github.com/user-attachments/assets/c6ca14a6-7b32-4eec-bc3a-18daabe4ff01)

## Server

![WhatsApp Image 2025-03-27 at 11 36 22_65abfcb1](https://github.com/user-attachments/assets/2ada0e03-7462-4839-8b3d-d3494fca9df9)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
