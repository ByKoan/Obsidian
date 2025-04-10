Las ``cabeceras`` mas usadas son las siguientes:
### [[stdio.h]]: 

```c
#include <stdio.h>
```

Cabecera para estándar input and output, en general la usaremos cuando queramos que el usuario nos ingrese un valor 

En ella tenemos una [[Funciones|función]], la cual es ``printf()`` para imprimir o devolver valores en pantalla, para usarla deberemos de especificar el [[Tipos_de_datos|tipo de dato]] que vamos a imprimir en los paréntesis, (Si es un texto que no lo almacene una [[Variables|variable]] lo imprimiremos con doble comillas) y fuera de las comillas poner el nombre de la variable a la que estamos accediendo, ejemplos:
```c
printf("%d", num);
printf("Hello World!");
```
### [[stdint.h]]: 

```c
#include <stdint.h>
```

![[Pasted image 20240909121252.png|700]]

https://en.wikibooks.org/wiki/C_Programming/stdint.h

| Specifier  | Signing  | Bits | Bytes | Minimum Value                                    | Maximum Value                                       |
| ---------- | -------- | ---- | ----- | ------------------------------------------------ | --------------------------------------------------- |
| `int8_t`   | Signed   | 8    | 1     | −27 which equals ``−128``                        | 27 − 1 which is equal to ``127``                    |
| `uint8_t`  | Unsigned | 8    | 1     | ``0``                                            | 28 − 1 which equals ``255``                         |
| `int16_t`  | Signed   | 16   | 2     | −215 which equals ``−32,768``                    | 215 − 1 which equals ``32,767``                     |
| `uint16_t` | Unsigned | 16   | 2     | ``0``                                            | 216 − 1 which equals ``65,535``                     |
| `int32_t`  | Signed   | 32   | 4     | −231 which equals ``−2,147,483,648``             | 231 − 1 which equals ``2,147,483,647``              |
| `uint32_t` | Unsigned | 32   | 4     | ``0``                                            | 232 − 1 which equals ``4,294,967,295``              |
| `int64_t`  | Signed   | 64   | 8     | −263 which equals ``−9,223,372,036,854,775,808`` | 263 − 1 which equals ``9,223,372,036,854,775,807``  |
| `uint64_t` | Unsigned | 64   | 8     | ``0``                                            | 264 − 1 which equals ``18,446,744,073,709,551,615`` |

Cabecera para ciertos [[Tipos_de_datos|tipos de datos]] en concreto los cuales suelen ser ``unsigned int`` o ``signed int``, con ella podremos definir la cantidad de los 2 tipos mencionados anteriormente ej.:
```c
uint64_t unsigned_var  = 0; 
int64_t  signed_var = 0;
```

### [[Math.h]]: 

```c
#include <math.h>
```

C por defecto solo trae las operaciones de sumar, restar, multiplicar, dividir y modular.
Hay es donde entra en juego esta cabecera para ayudarnos con funciones extras para otras operaciones, entre otras: 

