# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
```
# echo-server.py


import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)

```

```
Client Code:
# echo-client.py


import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Yuva krishna k  ")
    data = s.recv(1024)


print(f"Received {data!r}")

```
## OUTPUT:
## server:
![Screenshot 2024-09-09 190946](https://github.com/user-attachments/assets/c74e4a70-8d70-469e-adc0-d80acdd9f9a9)
## client:
![Screenshot 2024-09-09 190935](https://github.com/user-attachments/assets/79a5332e-5f27-4ee7-9719-0ea6b5027bbd)


## RESULT:
The program is executed successfully
