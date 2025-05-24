# Echoserver
Echo server and client using python socket
## Name: Shanmuga Raj.K
## Reg no: 212223040192
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

SERVER.PY:
~~~
import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    print("Server is listening...")

    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
~~~
CLIENT.PY:
~~~
import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    message = "Hello, world!"
    s.sendall(message.encode())
    data = s.recv(1024)
    print(f"Received {data.decode()}")
~~~
## OUTPUT:

![Screenshot 2025-03-14 184834](https://github.com/user-attachments/assets/84533438-45a7-4c14-97cf-8b06aa1bd1d4)

![Screenshot 2025-03-14 184928](https://github.com/user-attachments/assets/eb3bb58f-2e9a-4cfa-b2d2-541b1b938517)

![Screenshot 2025-03-14 190434](https://github.com/user-attachments/assets/adb15e36-93d4-49a6-831b-3301dcb33a6c)

![Screenshot 2025-03-14 190514](https://github.com/user-attachments/assets/87c3eb8a-2f34-48f2-9724-d4f1e55e3911)


## RESULT:
The program is executed successfully
