***Mecanismos para la comunicación entre procesos (IPC) que permite que dos programas se comuniquen ya sea en la misma maquina o en otra***

### Conceptos básicos:

- ***Socket: punto final de comunicación. Similar a un archivo pero en lugar de leer y escribir datos en un disco se leen y escriben datos a través de la red***
- ***Tipos de sockets:***

| Socket      | Descripcion                                                    |
| ----------- | -------------------------------------------------------------- |
| SOCK_STREAM | Proporciona comunicacion orientada a TCP                       |
| SOCK_DGRAM  | Proporciona comunicacion orientada a UDP                       |
| SOCK_RAW    | Permite acceso directo a protocolos subyacentes como IP o ICMP |
- ***Dominios (Familias):***

| Tipo     | Descripcion                              |
| -------- | ---------------------------------------- |
| AF_INET  | IPv4                                     |
| AF_INET6 | IPv6                                     |
| AF_UNIX  | Comunicacion de procesos locales de Unix |
- ***Direcciones:***
	- Para IPv4 se utiliza la estructura `struct sockaddr_in`
	- Para IPv6 se utiliza `struct sockaddr_in6`

### Flujo típico de Programación:

- ***Creación del socket (función `socket()`):***

```c
int socket(int domain, int type, int protocol);
```

```c
int sockfd = socket(AF_INET, SOCK_STREAM, 0);
if (sockfd < 0) {
    perror("Error al crear socket");
    exit(EXIT_FAILURE);
}
```

- ***Vincular un socket al puerto (Servidor):***
	- Función `bind()`

```c
int bind(int sockfd, const struct sockaddr *addr, socklen_t addrlen);
```

```c
struct sockaddr_in server_addr;
server_addr.sin_family = AF_INET;
server_addr.sin_addr.s_addr = INADDR_ANY;  // Escucha en todas las interfaces
server_addr.sin_port = htons(8080);       // Puerto 8080

if (bind(sockfd, (struct sockaddr *)&server_addr, sizeof(server_addr)) < 0) {
    perror("Error al enlazar el socket");
    exit(EXIT_FAILURE);
}
```

- ***Escuchar conexiones (Servidor):***
	- Función `listen()`

```c
int listen(int sockfd, int backlog);
```

```c
if (listen(sockfd, 5) < 0) {  // Máximo 5 conexiones en cola
    perror("Error al escuchar");
    exit(EXIT_FAILURE);
}
```

- ***Aceptar conexiones (Servidor):
	- Función `accept()`

```c
int accept(int sockfd, struct sockaddr *addr, socklen_t *addrlen);
```

```c
struct sockaddr_in client_addr;
socklen_t client_len = sizeof(client_addr);
int new_sock = accept(sockfd, (struct sockaddr *)&client_addr, &client_len);
if (new_sock < 0) {
    perror("Error al aceptar conexión");
    exit(EXIT_FAILURE);
}
```

- ***Conectarse a un servidor (Cliente):***
	- Función `connect()`

```c
int connect(int sockfd, const struct sockaddr *addr, socklen_t addrlen);
```

```c
struct sockaddr_in server_addr;
server_addr.sin_family = AF_INET;
server_addr.sin_port = htons(8080);
inet_pton(AF_INET, "127.0.0.1", &server_addr.sin_addr);  // Dirección IP del servidor

if (connect(sockfd, (struct sockaddr *)&server_addr, sizeof(server_addr)) < 0) {
    perror("Error al conectar al servidor");
    exit(EXIT_FAILURE);
}
```

- ***Enviar y recibir datos (Funciones `send()` y `recv()`):*** 

```c
ssize_t send(int sockfd, const void *buf, size_t len, int flags);
ssize_t recv(int sockfd, void *buf, size_t len, int flags);
```

```c
char buffer[1024] = "Hola, servidor!";
send(sockfd, buffer, strlen(buffer), 0);

memset(buffer, 0, sizeof(buffer));  // Limpiar buffer
recv(sockfd, buffer, sizeof(buffer), 0);
printf("Mensaje recibido: %s\n", buffer);
```

- ***Cerrar el socket con la función `close()`***

```c
close(sockfd);
```

### Ejemplo completo:

```c
// Servidor

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>

int main() {
    int sockfd, new_sock;
    struct sockaddr_in server_addr, client_addr;
    char buffer[1024];
    socklen_t addr_len;

    sockfd = socket(AF_INET, SOCK_STREAM, 0);
    if (sockfd < 0) {
        perror("Error al crear socket");
        exit(EXIT_FAILURE);
    }

    server_addr.sin_family = AF_INET;
    server_addr.sin_addr.s_addr = INADDR_ANY;
    server_addr.sin_port = htons(8080);

    if (bind(sockfd, (struct sockaddr *)&server_addr, sizeof(server_addr)) < 0) {
        perror("Error al enlazar");
        close(sockfd);
        exit(EXIT_FAILURE);
    }

    if (listen(sockfd, 5) < 0) {
        perror("Error al escuchar");
        close(sockfd);
        exit(EXIT_FAILURE);
    }

    printf("Esperando conexiones en el puerto 8080...\n");
    addr_len = sizeof(client_addr);
    new_sock = accept(sockfd, (struct sockaddr *)&client_addr, &addr_len);
    if (new_sock < 0) {
        perror("Error al aceptar conexión");
        close(sockfd);
        exit(EXIT_FAILURE);
    }

    recv(new_sock, buffer, sizeof(buffer), 0);
    printf("Mensaje recibido: %s\n", buffer);
    send(new_sock, "Hola, cliente!", 14, 0);

    close(new_sock);
    close(sockfd);
    return 0;
}
```

```c
// Cliente

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>

int main() {
    int sockfd;
    struct sockaddr_in server_addr;
    char buffer[1024] = "Hola, servidor!";

    sockfd = socket(AF_INET, SOCK_STREAM, 0);
    if (sockfd < 0) {
        perror("Error al crear socket");
        exit(EXIT_FAILURE);
    }

    server_addr.sin_family = AF_INET;
    server_addr.sin_port = htons(8080);
    inet_pton(AF_INET, "127.0.0.1", &server_addr.sin_addr);

    if (connect(sockfd, (struct sockaddr *)&server_addr, sizeof(server_addr)) < 0) {
        perror("Error al conectar al servidor");
        close(sockfd);
        exit(EXIT_FAILURE);
    }

    send(sockfd, buffer, strlen(buffer), 0);
    memset(buffer, 0, sizeof(buffer));
    recv(sockfd, buffer, sizeof(buffer), 0);
    printf("Mensaje recibido del servidor: %s\n", buffer);

    close(sockfd);
    return 0;
}
```