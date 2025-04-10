### Bloque ".data":

- Aquí declararemos nuestras variables y le asignaremos sus valores, Ejemplo:

```c
.data // Initialized global data
a: .long 2 // int a = 2;
b: .long 3 // int b = 3;
```

 Declaramos que a sea int (En ASM "long") con el valor 2
 Declaramos que b sea int con el valor 3

### Bloque ".bss":

- Contiene las variables que declaremos e inicialicemos. En este caso dos longs (INT de C), en este caso la variable 'r' **de 4 bytes** (long) **alineada a 4 bytes**

```c
.bss // Unitialized global data
.comm r,4,4 // int r;
```

### Bloque ".text":

- Contendrá las instrucciones del programa:
	- ***El bloque ".global main" inicia la función main con la llama al sistema***

```c
.text // Code segment
.global main // Inicia la funcion main del programa
```

### Bloque main:

- Sera donde empiece el funcionamiento del programa:

```c
main:
 movl a, %eax // a -> eax
 //Mov viene del ingles "Mover", lo usaremos para mover
 addl b, %eax // b + eax -> eax
 // Add viene del ingles "añadir", lo usaremos para sumar
 movl %eax, r // eax -> r
```

### Bloque retorno de Linux:

- El programa ya acabo por lo cual tendremos que retornar a Linux de la siguiente manera:
	- Normalmente se retorna un 0.
	- Copiamos el resultado de la ejecución (Variable 'r') al **ebx**
	- Copiamos un '1' al  registro **eax**
	- Llamamos a la interrupción **0x80**, en el caso de que el registro **eax** valga '1' termina la ejecución del programa devolviendo el contenido del registro **ebx** al SO

```c
 // movl $0, %ebx // Retorna 0 (Lo normal)
 movl r, %ebx // Retorna r (El byte mas bajo)
 movl $1 , %eax
 int $0x80
```
