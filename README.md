## EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
### DATE :20-03-2023

### AIM :

To write a python program to perform sliding window protocol.

### ALGORITHM :
```
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACKsignal to client.
6.Stop the program
```
### PROGRAM :
```
Developed By: Vishwa Rathinam S
Reg No: 212221240063
```
### CLIENT:
 ```python
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
### SERVER:
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode()
```
### OUTPUT :

### CLIENT:
![image](https://user-images.githubusercontent.com/122860624/242975896-9883f30e-f736-4f40-88c2-96622746b7f5.png)

### SERVER:
![image](https://user-images.githubusercontent.com/122860624/242976093-9f36672c-5f97-4af1-b5d1-7ec7652fc5a2.png)

### RESULT:

Thus, python program to perform stop and wait protocol And Sliding Window Protocol was successfully executed.
