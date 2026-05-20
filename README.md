# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
1)server.py
```

import socket 
# Create socket 
server = socket.socket() 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
# Listen for client 
server.listen(1) 
print("Server waiting for connection...") 
# Accept client 
client, addr = server.accept() 
print("Connected to:", addr) 
# Ask filename 
filename = input("Enter file name to send:") 
# Open and send file 
with open(filename, "rb") as file: 
    data = file.read() 
client.send(data) 
print("File sent successfully") 
# Close connections 
client.close() 
server.close() 
```
2)client.py
```
import socket 
# Create socket 
client = socket.socket() 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
# Save file name 
save_name = input("Enter name to save file: ") 
# Receive data 
data = client.recv(1000000) 
# Save file 
with open(save_name, "wb") as file: 
    file.write(data) 
print("File received successfully") 
# Close connection 
client.close()
```
## OUPUT
<img width="1918" height="1058" alt="Screenshot 2026-05-20 113602" src="https://github.com/user-attachments/assets/db531239-118d-4d44-9bb2-8466a15a73f8" />
<img width="1836" height="282" alt="Screenshot 2026-05-20 113613" src="https://github.com/user-attachments/assets/64036ac8-a42c-480a-acfa-30ef415bdade" />
<img width="1918" height="737" alt="Screenshot 2026-05-20 113646" src="https://github.com/user-attachments/assets/7fb21d0b-3979-4a9d-9d78-e543ca0731b5" />
<img width="1437" height="236" alt="Screenshot 2026-05-20 113625" src="https://github.com/user-attachments/assets/11f737bc-9e89-4a5e-8a61-75e697c0330d" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
