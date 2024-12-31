https://www.geeksforgeeks.org/c-pointers/

***Al igual que [[Memoria dinamica|Memoria dinámica]] son el padre nuestro de cada día en c***

- Existen diferentes tipos de punteros:

### Punteros enteros:
- ***Almacena la dirección de una variable de tipo entero***

```c
#include <stdio.h>
int main() {
    int x = 42;
    int *ptr = &x;  // ptr almacena la dirección de x.

    printf("Valor de x: %d\n", *ptr);  // Accede al valor de x mediante ptr.
    printf("Dirección de x: %p\n", ptr);  // Muestra la dirección de x.

    *ptr = 100;  // Modifica x mediante el puntero.
    printf("Nuevo valor de x: %d\n", x);
    return 0;
}
```
### Punteros de matriz (Strings):
- ***Almacena la dirección de una variable String***

```c
#include <stdio.h>
int main() {
    char *ptr = "Hola mundo";  // El puntero apunta al inicio del string.

    printf("String completo: %s\n", ptr);

    return 0;
}
```
### Punteros de estructura:
- ***Almacena la dirección de una estructura y permite acceder a sus elementos:***

```c
#include <stdio.h>
struct Persona {
    char nombre[50];
    int edad;
};

int main() {
    struct Persona p1 = {"Juan", 30};
    struct Persona *ptr = &p1;  // ptr almacena la dirección de p1.

    printf("Nombre: %s\n", ptr->nombre);  // Accede al miembro 'nombre'.
    printf("Edad: %d\n", ptr->edad);      // Accede al miembro 'edad'.

    ptr->edad = 35;  // Modifica 'edad' mediante el puntero.
    printf("Nueva edad: %d\n", ptr->edad);

    return 0;
}
```
### Punteros a función:
- ***Almacena la dirección de una función y permite llamarla de forma dinámica***

```c
#include <stdio.h>
void saludo() {
    printf("Hola, mundo!\n");
}

void despedida() {
    printf("Adiós, mundo!\n");
}

int main() {
    void (*funcPtr)();  // Declara un puntero a función.

    funcPtr = saludo;  // Apunta a la función saludo.
    funcPtr();  // Llama a saludo.

    funcPtr = despedida;  // Cambia a la función despedida.
    funcPtr();  // Llama a despedida.

    return 0;
}

```
### Punteros dobles:
- ***Almacena la dirección de otro puntero:***

```c
#include <stdio.h>
int main() {
    int x = 10;
    int *ptr = &x;  // Puntero a x.
    int **dptr = &ptr;  // Puntero a ptr.

    printf("Valor de x: %d\n", **dptr);  // Accede a x mediante el puntero doble.
    printf("Dirección de x: %p\n", *dptr);  // Dirección de x.

    **dptr = 20;  // Modifica x mediante el puntero doble.
    printf("Nuevo valor de x: %d\n", x);

    return 0;
}
```
### Punteros NULL:
- ***Puntero que no apunta a ninguna dirección valida, usado para inicializar de forma segura:***

```c
#include <stdio.h>
int main() {
    int *ptr = NULL;  // Inicializa ptr como un puntero nulo.

    if (ptr == NULL) {
        printf("El puntero no apunta a nada.\n");
    }

    // Intentar desreferenciar un puntero NULL causa errores de ejecución.
    return 0;
}
```
### Punteros Vacíos (VOID):
- ***Pueden almacenar la dirección de cualquier tipo de dato pero deber ser convertido antes de desreferenciarse:***

```c
#include <stdio.h>
int main() {
    int x = 10;
    float y = 20.5;
    void *ptr;

    ptr = &x;  // ptr apunta a un entero.
    printf("Valor de x: %d\n", *(int *)ptr);  // Cast a (int *).

    ptr = &y;  // ptr apunta a un flotante.
    printf("Valor de y: %.1f\n", *(float *)ptr);  // Cast a (float *).

    return 0;
}
```
### Punteros constantes:
- ***No puede cambiar la dirección a la que apunta, pero el valor en esa dirección puede modificarse***

```c
#include <stdio.h>
int main() {
    int x = 10, y = 20;
    int *const ptr = &x;  // Puntero constante a un entero.

    *ptr = 15;  // Cambiar el valor es válido.
    // ptr = &y;  // Error: no se puede cambiar la dirección.

    printf("Valor de x: %d\n", x);

    return 0;
}
```