***En c la memoria dinámica es como el padre nuestro de cada día***

- Existen varias formas de reservar memoria dinámica:
### MALLOC:
- ***Memory allocator:*** devuelve un puntero ``void`` al espacio asignado o ``NULL`` si no hay suficiente memoria/no se asigno correctamente. Por eso lo mas común cuando reservamos memoria es compararlo con ``NULL`` y así nos aseguramos de que funciono.
- **Si usamos MALLOC deberemos de usar** ***MEMSET*** **para una vez reservada memoria ponerla a 0 y modificarlo con los datos que usaremos.***
- ***MALLOC*** Hace uso de la cabecera ``stdlib.h`` y ***Memset*** usa la cabecera ```string.h``` 
Ejemplo:

```c 
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main () {

    int* ptr; // Iniciamos un ptr int
    ptr = (int*)malloc(sizeof(int)); // Reservamos memoria para su espacio
    if (ptr == NULL) { //Comparamos si fue asignada o no
        printf("La memoria no fue asignada.\n");
    } else {
        printf("La memoria fue asignada correctamente.\n");
    }
    memset(ptr, '0',sizeof(int)); // Ponemos la memoria a 0
    printf("Dec: %d, Hex: %x, Unsigned: %u\n", ptr,ptr,ptr); // Imprimimos la direccion de memoria

	free(ptr); // Nunca olvidarse de liberar memoria
    return 0;
}
```

### CALLOC:
- ***CALLOC*** **es muy parecida a MALLOC con la diferencia de que** ***CALLOC*** **ya te reserva la memoria estableciéndola a 0** 
Ejemplo:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {

    long *buffer;
    buffer = (long *)calloc( 40, sizeof( long ) );
    if (buffer == NULL){
        printf("La memoria no se pudo reservar.\n");
    } else {
        printf("La memoria se reservo correctamente.\n");
        printf("Dec: %d, Hex: %x, Unsigned: %u\n",
        buffer,buffer,buffer);
    }

    free(buffer);
    return 0;

}
```

