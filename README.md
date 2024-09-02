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
 
CLIENT: 
 ```py
import socket 
s=socket.socket() 
s.listen(5) 
c,addr=s.accept() 
while True: 
    i=input("Enter a data: ") 
    c.send(i.encode()) 
    ack=c.recv(1024).decode() 
    if ack: 
        print(ack) 
        continue 
    else: 
        c.close() 
        break 
``` 
SERVER: 
 ```py
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT: 
![Screenshot 2024-09-02 085314](https://github.com/user-attachments/assets/857d43fa-0fd1-45ab-a5ff-91f047fdf45e)
 
SERVER: 
![Screenshot 2024-09-02 085332](https://github.com/user-attachments/assets/b1efd2e5-f761-49b3-a67e-c366602ef64c)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
