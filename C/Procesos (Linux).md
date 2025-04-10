***Son instancias en ejecución de un programa. Para crear y manejar procesos en C, se suelen usar funciones del sistema proporcionadas por el SO especialmente en entornos UNIX/Linux***

### ¿ Que es un proceso ?

- ***Código del programa en ejecución***
- ***Un espacio de memoria asignado***
- ***Información del sistema (Archivos abiertos, variables de entorno, etc...)***
- ***Estado del proceso (Ejecutando, esperando, terminado etc...)***

### Creación de procesos:

- ***En UNIX/Linux, los procesos se crean usando la función `fork()`. Esta función esta definida en la header `<unistd.h>`***

- ***Prototipo:***
```c
pid_t fork(void);
```

- ***Funcionamiento:***
	- ***Crea un proceso hijo duplicando el proceso padre***
	- ***El proceso hijo es una copia exacta del padre, excepto:***
		- Su ID de proceso **(PID)** es único
		- Tiene su propio espacio de memoria
	- ***Retorna:***
		- `0` al proceso hijo
		- El PID del hijo al proceso padre
		- Un valor negativo `-1` si la creación falla

- ***Ejemplo básico con `fork()`:***

```c
#include <stdio.h>
#include <unistd.h>

int main() {
    pid_t pid = fork();

    if (pid < 0) {
        // Error al crear el proceso
        perror("Error al crear el proceso");
    } else if (pid == 0) {
        // Código ejecutado por el proceso hijo
        printf("Soy el proceso hijo, mi PID es %d\n", getpid());
    } else {
        // Código ejecutado por el proceso padre
        printf("Soy el proceso padre, mi PID es %d, y mi hijo tiene PID %d\n", getpid(), pid);
    }

    return 0;
}
```

### Ejecución de nuevos programas en el proceso hijo:

- ***Para ejecutar un programa diferente en un proceso, puedes usar las funciones de la familia `exec`. Definidas en `<unistd.h>`***
- ***Funciones principales:***
	- `execl()` ***Carga y ejecuta un programa usando una lista de argumentos (como parámetros)***
	- `execv()` ***Similar a `excecl()` pero usa un arreglo de punteros en lugar de una lista de argumentos***
	- `execvp()` ***Busca el programa en el PATH antes de ejecutarlo***
	- `execve()` ***Función mas genérica, permite especificar el entorno***

- **Ejemplo con `execl()`:**

```c
#include <stdio.h>
#include <unistd.h>

int main() {
    pid_t pid = fork();

    if (pid == 0) {
        // Proceso hijo
        printf("Ejecutando 'ls' en el hijo\n");
        execl("/bin/ls", "ls", "-l", NULL);
        perror("Error al ejecutar ls");
    } else if (pid > 0) {
        // Proceso padre
        printf("Proceso padre esperando al hijo\n");
    } else {
        perror("Error al crear el proceso");
    }

    return 0;
}
```