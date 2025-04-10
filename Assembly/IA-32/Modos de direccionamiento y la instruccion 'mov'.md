***Una instrucción típicamente trabaja sobre uno o mas operadores, por ejemplo: la instrucción 'mov' copia el valor de un primer operador a un segundo operador (Que será un registro o una posición de memoria)***

Formato de las instrucciones:

```c
INSTRUCCION OPERADOR1 OPERADOR2
```

***Los modos de direccionamiento sirven para indicar donde están los operadores de una instrucción. Tenemos los siguientes:***

- Inmediato: '$100' el numero 100 (El operador de destino nunca puede ser inmediato)
- Registro '%eax' 
- Memoria

### Instrucción MOV:

***Ejemplos de 'mov': Asignar un 0 al registro EAX:

```c
movl $0, %eax
```

***Copiar el valor del registro EAX (Acumulador) al registro EBX (Base):***

```c
movl %eax, %ebx
```

***Asignar el valor 1000 al registro EBX (Base):***

```c
movw $1000, %bx
```

***Asignar el valor ASCII 'A' al registro AL 

```C
movb $'A', %al
```

***La instrucción MOV termina con l (LONG), w (WORD) o b (BYTE) dependiendo del tipo de dato con el que este operando, no hace falta indicarle el tipo de dato pero es una buena practica***

### Modos de direccionamiento:
- ***Memoria normal (%eax) = valor en la posición de memoria contenida en el registro eax. Ejemplo:***

```c
movl %ecx, %eax // Lee el long contenido en la posicion de mem en ecx y la copia a eax
```

- ***Memoria desplazamiento (Base) = 8(%ebp) valor en la posición de memoria resultante de sumar 8 al contenido del registro EBP. Ejemplo:***

```c
movl 8(%ebp), %edx // Lee el long contenido en la posicion de la memoria ebp + 8 y la copia al registro edx
```

- ***El desplazamiento tanto puede ser una constante como el nombre de una variable (En este ultimo caso puede ser una constante como el nombre de una variable (En este ultimo caso el valor del desplazamiento será la posición de la memoria donde esta variable empieza)***

*PAG 26*