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
## server:
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
filename = input("Enter file name to send: ") 
# Open and send file 
with open(filename, "rb") as file: 
    data = file.read() 
    client.send(data) 
print("File sent successfully") 
# Close connections 
client.close() 
server.close()
```
## client:
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
## sample:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/65496db1-424f-46bd-a709-22e707a773cc" />
## server:

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dfb0dfbc-bd44-492b-9b6d-b2ba37c3e9f7" />

## client:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/09884589-3ddf-41c9-b6e4-789ecf0afff8" />
## recieved:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b6de8013-be69-4d6e-818c-c5b9ab3b0dde" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
