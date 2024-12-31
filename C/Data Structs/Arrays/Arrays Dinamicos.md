***Estructuras que permiten al programador trabajar con colecciones de datos cuyo tamaño puede cambiar durante la ejecución del programa. A diferencia de los arrays estáticos cuyo tamaño lo tienes que definir en tiempo de compilación los arrays dinámicos permiten manejar tamaños variables mediante la asignación y liberación de [[Memoria dinamica]]***

### Array dinámico:

- ***Estructura de datos que se crea en el Heap, usando funciones de C estándar para gestionar su memoria. Su tamaño se puede definir en tiempo de ejecución y modificarse si es necesario***

### Gestión de Memoria dinámica en Arrays Dinámicos:

- ***Usaremos varias funciones para gestionar la memoria de los arrays dinámicos: `malloc()`, `calloc()`, `realloc()` y `free()`***

### Ventajas:

- ***Flexibilidad: Permiten definir el tamaño del array en tiempo de ejecución***
- ***Eficiencia de memoria: Usan solo la memoria necesaria***
- ***Redimensionamiento: Se pueden expandir o reducir usando `realloc()`***

### Desventajas:

- ***Complejidad: El programador es responsable de gestionar la memoria, lo que puede generar errores si no se libera correctamente.***
- ***Rendimiento: Las operaciones como redimensionar pueden ser costosas en términos de tiempo ya que pueden implicar copiar datos***
- ***Fugas de memoria: Si olvidas liberar la memoria, quedara ocupada hasta que termine el programa***

### Ejemplo básico de arrays dinámicos:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, i;

    printf("Ingrese el tamaño del array: ");
    scanf("%d", &n);

    // Asignar memoria dinámicamente
    int *array = (int *)malloc(n * sizeof(int));
    if (array == NULL) {
        printf("Error al asignar memoria\n");
        return 1;
    }

    // Inicializar el array
    for (i = 0; i < n; i++) {
        array[i] = i + 1;
    }

    // Imprimir el contenido del array
    printf("Elementos del array:\n");
    for (i = 0; i < n; i++) {
        printf("%d ", array[i]);
    }
    printf("\n");

    // Cambiar el tamaño del array
    printf("Ingrese el nuevo tamaño del array: ");
    scanf("%d", &n);

    array = (int *)realloc(array, n * sizeof(int));
    if (array == NULL) {
        printf("Error al redimensionar memoria\n");
        return 1;
    }

    // Llenar nuevos elementos si el tamaño aumentó
    for (i = 0; i < n; i++) {
        array[i] = i + 1; // Reasignar valores
    }

    // Imprimir el contenido del array redimensionado
    printf("Elementos del array redimensionado:\n");
    for (i = 0; i < n; i++) {
        printf("%d ", array[i]);
    }
    printf("\n");

    // Liberar memoria
    free(array);

    return 0;
}
```