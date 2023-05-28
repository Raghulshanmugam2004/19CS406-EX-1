# 19CS406-EX-1 IMPLEMENTATION OF STOP AND WAIT PROTOCOL
# DATE : 
16-03-2023
# AIM :
To write a python program to perform stop and wait protocol
# ALGORITHM :

    1.Start the program.

    2.Get the frame size from the user

    3.To create the frame based on the user request.
    
    4.To send frames to server from the client side.
    
    5.If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
    
    6.Stop the program

# CLIENT PROGRAM :
```
## Developed By : RAGHUL S
## Reg No : 212222040128
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
	i=input("ENter a data:")
	c.send(i.encode())
	ack=c.recv(1024).decode()
	if ack:
		print(ack)
		continue
	else:
		c.close()
		break
   ```

# SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
```
# CLIENT OUTPUT:
![image](https://github.com/Raghulshanmugam2004/19CS406-EX-1/assets/119561118/a9cbeae9-92e8-433e-9747-94a84a3e89eb)

# SERVER OUTPUT:
![image](https://github.com/Raghulshanmugam2004/19CS406-EX-1/assets/119561118/0895da3b-2eee-4604-ab50-50bbaec2ad8a)

# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
