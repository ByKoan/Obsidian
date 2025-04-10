***En el IA 32 tenemos los siguiente tipos de datos:***

| TIpo                  | Representacion | Tamaño  |
| --------------------- | -------------- | ------- |
| Byte                  | b              | 8 bits  |
| Word                  | w              | 16 bits |
| Long                  | l              | 32 bits |
| Posiciones de memoria |                | 32 bits |
***En el IA 32 si un dato tiene mas de 1 byte, el byte de mas peso se guardara en la posicion mas alta de la memoria. A esto se le llama utilizar el formato "little endian"***

***Aparte por un tema de eficiencia los datos se guardaran "alineados en memoria" esto significa que un dato de 4 bits se almacenara empezando en una direccion de memoria divisible por 4 y un dato de 2 bits en una direccion divisible por 2. SI no lo hicieramos asi acceder a estos datos requeriria dos accesos a memoria***

***El equivalente de C de un tipo INT es un LONG, de un CHAR es un BYTE, los WORD se usan  muy poco (Herencia de arquitectura de 16 bits en las cuales solo habian registros de 8 y 16 bits)***