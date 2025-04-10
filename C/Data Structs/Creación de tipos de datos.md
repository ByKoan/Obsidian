``Typedef`` con el podemos crear nuestros tipos de datos o cambiarle el nombre a los ya existentes.

Podemos elegir entre cambiarle el nombre a los tipos de [[Tipos_de_datos|Datos]] existentes.

Sintaxis:
```c
typedef tipo_de_dato nuevo_nombre1, nuevo_nombre2, ...;
```
Ejemplo:
```c
typedef char FlagType;
```

Crear nuestros tipos de datos a traves de una estructura:
 
Sintaxis:
```c
typedef struct nombre_del_dato {
	nuestros_datos_aqui;
} nombre_del_dato; 
```
Ejemplo:
```c
typedef struct Nodes {
    struct Nodes * NextNode; 
    struct Nodes * LastNode; 
    
} Nodes, *PNodes;
```

```c
PNodes MiPtr1 = NULL;
Nodes *MiPtr2 = NULL;
```