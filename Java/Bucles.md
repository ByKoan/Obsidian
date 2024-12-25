### Bucle While:

- ***Bucle que permite repetir un código especifico mientras que se de una condición:***

```java
while (condición) {
    // Bloque de código que se ejecuta mientras la condición sea verdadera
}

int contador = 1;

while (contador <= 5) {
    System.out.println("Contador: " + contador);
    contador++; // Incrementa el contador para evitar un bucle infinito
}
```

- ***Bucle While Infinito:***

```java
while (true) {
    System.out.println("Esto es un bucle infinito");
}
```

- ***Si queremos terminar un bucle while al igual que en el switch-case usamos la palabra clave `break` si queremos que continúe usamos `continue`***

```java
int contador = 1;

while (contador <= 10) {
    if (contador == 5) {
        break; // Salir del bucle cuando el contador sea 5
    }
    System.out.println("Contador: " + contador);
    contador++;
}

```

- ***Bucle While Anidado:***

```java
int i = 1;

while (i <= 5) {
    int j = 1;
    while (j <= 5) {
        System.out.print(i * j + "\t");
        j++;
    }
    System.out.println();
    i++;
}
```

### Bucle DO-WHILE:

- ***Ejecuta el código al menos una vez, incluso aunque la condición que se evalúa al final sea falsa:***

```java
do {
    // Bloque de código a ejecutar
} while (condición);

int contador = 1;

do {
    System.out.println("Contador: " + contador);
    contador++;
} while (contador <= 5);
```

### Bucle FOR:

- ***Muy parecido al bucle WHILE, permite que se repita un código mientras se da una condición***

```java
for (inicialización; condición; actualización) {
    // Bloque de código que se ejecuta mientras la condición sea verdadera
}

for (int i = 1; i <= 5; i++) {
    System.out.println("Valor de i: " + i);
}
```

- ***En los bucles FOR podemos tener mas de una variable separado por comas:***

```java
for (int i = 1, j = 10; i <= 5 && j >= 6; i++, j--) {
    System.out.println("i: " + i + ", j: " + j);
}
```

- ***Bucle FOR anidado:***

```java
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
        System.out.println("i: " + i + ", j: " + j);
    }
}
```

