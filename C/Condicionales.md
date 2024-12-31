### Condicional IF:
- ***Estructura de control que permite ejecutar un bloque de código si una condición especifica se cumple:***
```c
#include <stdio.h>

int main () {
	int num1 = 5;
	if (num1 % 2 == 0) {
		printf("El numero es par.");
	} else {
		printf("El numero es impar.")
	}
}
```

- ***Para añadir mas condiciones usaremos else-if***

```c
#include <stdio.h>

int main() {
    int num = 10;
    if (num > 5) {
    printf("X es mayor que 5\n");
    } else if { 
    (num > 10) printf("X es mayor que 10\n");
    }
    
    return 0;
}
```

### Condicional Switch:
- ***Estructura de control que permite ejecutar bloques de código si se dan ciertos casos:***

```c
#include <stdio.h>

int main () {

int dia = 4;

switch (dia) {
	case 1:
		printf("Lunes");
		break // Salir del condicional
	case 2:	
		printf("Martes");
		break // Salir del condicional
		...
	default:
		printf("Opcion por defecto");
	}
	return 0;
}
```

