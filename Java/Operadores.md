***Símbolos que realizan operaciones sobre uno o mas operandos. Java soporta operadores para realizar operaciones aritméticas, lógicas, de comparación, asignación etc...***

### Operadores Aritméticos:

| Operado | Descripción    |
| ------- | -------------- |
| +       | Suma           |
| -       | Resta          |
| *       | Multiplicacion |
| /       | Division       |
| %       | Modulo         |
### Operadores Relacionales o de Comparación:

| Operador | Descripcion       |
| -------- | ----------------- |
| ==       | Igual a           |
| !=       | Distinto de       |
| >        | Mayor que         |
| <        | Menor que         |
| >=       | Mayor o igual que |
| <=       | Menor o igual que |
### Operadores Lógicos:

| Operador | Descripcion |
| -------- | ----------- |
| &&       | AND logico  |
| `        | OR Logico   |
| !        | NOT Logico  |
### Operadores de Asignación:

| Operador | Descripcion                   |
| -------- | ----------------------------- |
| =        | Asingacion                    |
| +=       | Asignacion con suma           |
| -=       | Asignacion con resta          |
| *=       | Asignacion con multiplicacion |
| /=       | Asignacion con division       |
| %=       | Asignacion con modulo         |
### Operadores Unarios:

| Operador | Descripcion                          |
| -------- | ------------------------------------ |
| +        | Indica un valor positivo (Implicito) |
| -        | Cambia el signo                      |
| ++       | Incrementa                           |
| --       | Decrementa                           |
| !        | Negacion Logica                      |
### Operadores Bit a Bit:

| Operador | Descripcion                   |
| -------- | ----------------------------- |
| &        | AND                           |
| `        | OR                            |
| ^        | XOR                           |
| ~        | Complemento a Bit             |
| <<       | Desplazamiento a la izquierda |
| >>       | Desplazamiento a la derecha   |
| >>>      | Desplazamiento sin signo      |
### Operadores Ternarios:

- ***Permite realizar una operación condicionar en una sola linea:***

```JAVA
int a = 5, b = 3;
int mayor = (a > b) ? a : b; // Si `a > b`, mayor es `a`, si no, es `b`
System.out.println(mayor); // 5
```

### Operadores de Instancia:

| Operador   | Descripcion                                  | Ejemplo                 | Resultado |
| ---------- | -------------------------------------------- | ----------------------- | --------- |
| instanceof | Comprueba si un objeto pertenece a una clase | "Hola" instaceof String | true      |
