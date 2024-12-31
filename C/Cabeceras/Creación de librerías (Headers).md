***Forma muy común de organizar código y hacer que sea mas modular y reutilizable***

### ¿ Que es un Header ?:

- ***Archivo de texto con la extensión `.h` que generalmente contiene:***
	- Declaración de funciones
	- Definición de constantes
	- Estructuras de datos
	- Macros

### Estructura básica de un archivo Header:

```c
#ifndef MI_HEADER_H    
#define MI_HEADER_H   

// Macros para que si no fue definida se defina

// Declaración de una función
void saludar(const char* nombre);

// Definición de una constante mediante macro
#define PI 3.14159

// Definición de una estructura
typedef struct {
    int x;
    int y;
} Punto;

#endif // Fin del bloque de protección contra inclusión múltiple
```

### Porque usar las macros `ifndef`, `define` y `endif`:
- ***Evitar que el contenido del header se incluya mas de una vez en un mismo archivo de código, esto se conoce como inclusión múltiple y puede causar errores al intentar redefinir funciones o variables***

#ifndef MI_HEADER_H: Verifica si la constante MI_HEADER_H no ha sido definida aún.
#define MI_HEADER_H: Define la constante para que, si el archivo se incluye nuevamente, no entre en la sección del código.
#endif: Termina el bloque de código que está protegido contra inclusión múltiple.

### Usar el archivo Header desde código C:

```c
#include <stdio.h>
#include "mi_header.h"  /

void saludar(const char* nombre) {
    printf("¡Hola, %s!\n", nombre);
} // Aunque se haya definido en el header tambien tiene que estar definido en el codigo fuente

int main() {
    // Uso de la función declarada en el header
    saludar("Juan");

    // Uso de la constante PI
    printf("El valor de PI es: %f\n", PI);

    // Uso de la estructura
    Punto p = {10, 20};
    printf("Punto: (%d, %d)\n", p.x, p.y);

    return 0;
}
```