***En C para leer por teclado tenemos varias funciones:***

### SCANF:

```c
int num1;

printf("Mete un numero aqui:");
scanf("%d", &num1);
```

### FGETS:

```C
#include <stdio.h>

int main() {
    char buffer[50]; // Espacio para almacenar la entrada del usuario

    printf("Ingrese un texto: ");
    fgets(buffer, sizeof(buffer), stdin); // Leer hasta 49 caracteres de la entrada

    printf("Texto ingresado: %s", buffer); // Mostrar lo que el usuario escribió

    return 0;
}
```
