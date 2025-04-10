***Estructuras de datos fijas en tiempo de compilación o al inicio del programa. Este enfoque es útil para aplicaciones con requisitos predecibles o recursos limitados:***

### Estructura de una tabla hash estática:

- ***Array fijo: Actúa como el almacenamiento principal***
- ***Un ''Hash function'': Determina la posición donde almacenar los datos***
- ***Una estrategia para manejar colisiones: Ya que diferentes claves pueden mapearse al mismo índice***

### Características principales:

- ***Tamaño fijo: Se define antes de compilar o al inicio y no cambia durante la ejecución***
- ***Rendimiento predecible: No hay necesidad de redimensionar, lo que hace que el rendimiento sea consistente***
- ***Uso limitado de memoria: Útil en sistemas embebidos o recursos restringidos***
- ***No apta para datos dinámicos: Si el numero de elementos excede la capacidad la tabla se desbordara***
### Implementación de una tabla hash:

```c
#include <stdio.h>
#include <string.h>

#define TABLE_SIZE 10

typedef struct {
    char key[50];
    int value;
} HashItem;

HashItem hashTable[TABLE_SIZE] = {0};

unsigned int hashFunction(const char *key) {
    unsigned int hash = 0;
    while (*key) {
        hash = (hash * 31) + *key;
        key++;
    }
    return hash % TABLE_SIZE;
}

void insert(const char *key, int value) {
    unsigned int index = hashFunction(key);

    while (hashTable[index].key[0] != '\0') {
        if (strcmp(hashTable[index].key, key) == 0) {
            hashTable[index].value = value;
            return;
        }
        index = (index + 1) % TABLE_SIZE;
    }

    strcpy(hashTable[index].key, key);
    hashTable[index].value = value;
}

int search(const char *key, int *value) {
    unsigned int index = hashFunction(key);

    while (hashTable[index].key[0] != '\0') {
        if (strcmp(hashTable[index].key, key) == 0) {
            *value = hashTable[index].value;
            return 1;
        }
        index = (index + 1) % TABLE_SIZE;
    }

    return 0;
}

void delete(const char *key) {
    unsigned int index = hashFunction(key);

    while (hashTable[index].key[0] != '\0') {
        if (strcmp(hashTable[index].key, key) == 0) {
            hashTable[index].key[0] = '\0';
            return;
        }
        index = (index + 1) % TABLE_SIZE;
    }
}

int main() {
    insert("key1", 10);
    insert("key2", 20);

    int value;
    if (search("key1", &value)) {
        printf("Found: key1 -> %d\n", value);
    } else {
        printf("Key not found\n");
    }

    delete("key1");

    if (search("key1", &value)) {
        printf("Found: key1 -> %d\n", value);
    } else {
        printf("Key not found\n");
    }

    return 0;
}
```

### Estrategias de manejo de colisiones:

- ***Open Addresing (Dirección abierta):
	- Linear probing
	- Quadratic probing
	- Double Hashing
- ***Separate Chaining (Encadenamiento separado):***
	- Cada celda de la tabla almacena una lista vinculada