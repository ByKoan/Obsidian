Los archivos `MakeFile` sirven para compilar proyectos grandes, que contengan muchos archivos o muchas flags mediante un único comando `mingw32-make`

En los `MakeFiles` podemos declarar valores como el compilador que usaremos los archivos que usaremos flags etc.:

### Compilador:

```c
CC = gcc // Con esto indicaremos que usaremos GCC para compilar archivos C
```

### Flags:

```c
CFLAGS = // Las flags aqui
```

### SRC:

```C
SRC = // El nombre del archivo .c
```
### Target:

```c
TARGET = // El nombre del programa aqui
```
### Compilar Target Final:

```c
// Pasar el programa a codigo objeto:

main: main.o 
	$(CC) /*Llamamos al compilador*/ $(CFLAGS) /*Llamamos a las flags*/ -o main main.o

// Compilando los objetos:

main.o: main.c 
	$(CC) $(CFLAGS) -c main.c

// Limpiamos archivos temporales

clean:
	rm -f *.o main
```


### Mostrar mensajes por consola:

- Función útil para mostrar cuando ha compilado o información en el proceso:

```c
@echo "Mensaje de ejemplo"
```

### Ejemplo completo:

```c
CC = gcc
CFLAGS = -Wall -Wextra -O2
SRC = main.c 
TARGET = MiPrograma.exe

$(TARGET): $(SRC)
	$(CC) $(CFLAGS) -o  $(TARGET)

@echo "Compilacion exitosa."
```