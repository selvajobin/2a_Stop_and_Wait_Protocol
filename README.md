# 2a_Stop_and_Wait_Protocol

### Name: SELVA JOBIN S
### Reg.NO: 212223220102
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
### CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
### SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### CLIENT
![306664559-5e7536db-fd1a-4b3f-9358-211a771e8100](https://github.com/selvajobin/2a_Stop_and_Wait_Protocol/assets/149985750/3492f6ab-09d0-45fa-bb17-783ac39a6bd3)


### SERVER
![306664797-08351b08-bc67-42a0-975a-88d1f145a355](https://github.com/selvajobin/2a_Stop_and_Wait_Protocol/assets/149985750/c84db50e-2f11-43cd-9484-d1687ae6b883)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
