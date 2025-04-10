Para mover datos usamos la instrucción **mov** con el tipo de dato que queremos mover.

```c
movl op1, op2 // Copiar un long de op1 a op2
movw op1, op2 // Copiar un word de op1 a op2
movb op1, op2 // Copiar un Byte de op1 a op2
```

Si necesitamos copiar de byte o word a un dato de mayor tamaño podremos usar la instrucción **movz** o **movs**

### Movz:
- Mueve el operando de byte o word extendiendo 0, significa que copia el operando 1 a la parte baja del operando 2 y pone '0' al resto del operando 2

```c
movz[bw|bl|wl] op1, op2
// bw = byte to word
// bl = byte to long
// wl = word to long
```

**Ejemplo:** Para mover un byte a un Long "extendiendo ceros" haríamos ***movzbl**

### Movs:

- No obstante si el numero es un entero con signo lo que nos interesaría es hacer un **movs**, que mueve el operando 1 al operando 2, "extendiendo el signo", significa que copia el operando 1 a la parte baja del operando 2 y copia el significado del operando 1 (su bit de mas peso, porque los enteros con signo los codificamos con complemento a 2) al resto de los bits del operando 2

En el siguiente ejemplo **al** vale '-1' y lo copiamos a **ebx**:

```c
movl $-1, %al
movsbl %al, %ebx
```

- *Usamos 'movs' en lugar de 'movz' ya que '-1' es '0xFF' en Hexadecimal y queremos que 'ebx' valga '-1' (0xFFFFFFFF) y no '0x000000FF' (+255)