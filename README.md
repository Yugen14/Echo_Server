# Echoserver

Echo server and client using python socket

# AIM:

To develop an echo server and client using python socket

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:

# Server code

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

# Client Code:

# echo-client.py

    import socket

    HOST = "127.0.0.1"  # The server's hostname or IP address

    PORT = 65432  # The port used by the server

    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:

    s.connect((HOST, PORT))
    
    s.sendall(b"Hello, world")
    
    data = s.recv(1024)
    
    print(f"Received {data!r}")

## OUTPUT:

![Screenshot from 2023-05-13 05-16-19](https://github.com/Kathir-2703/Echoserver/assets/64436376/9ea1858a-fe00-419d-9231-46b0392f048f)

![Screenshot from 2023-05-13 04-55-14](https://github.com/Kathir-2703/Echoserver/assets/64436376/0b472b77-964b-40a1-86a2-546e1478d3a0)

## RESULT:
The program is executed successfully
