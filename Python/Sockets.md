Pagina ref - https://realpython.com/python-sockets/
### HACIENDO ESTA PAGINA


### Principales funciones de sockets en Python:

- `socket()`
- `.bind()`
- `.listen()`
- `.accept()`
- `.connect()`
- `.connect_ex()`
- `.send()`
- `.recv()`
- `.close()`
### Sockets TCP:

- Se crean usando el objeto `socket.socket()` especificando el socket como `SOCK_SREAM` 

### Sockets UDP:

- Se crean con `socket.SOCK_DGRAM` 

![[Pasted image 20241219205140.png]]

### Código ejemplo (ECHO SERVER):
```python
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT)) # Indicas la IP y el Puerto del servidor
    s.listen() # Pones el servidor en escucha
    conn, addr = s.accept() # Aceptas peticiones
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
