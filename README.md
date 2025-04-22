# 2a_Stop_and_Wait_Protocol
### REG NO:212224230277
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

client
~~~
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
~~~
server
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Recieved".encode())
~~~

## OUTPUT

client output

![Screenshot 2025-04-12 114838](https://github.com/user-attachments/assets/4591be1b-9803-4e5a-8207-454bb7c64026)

server output

![Screenshot 2025-04-12 114843](https://github.com/user-attachments/assets/3e9c5c85-6e8a-460b-8900-6f6893c8d102)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
