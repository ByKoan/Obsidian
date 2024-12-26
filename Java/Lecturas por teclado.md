***Para leer datos por teclado tenemos la clase scanner:***

```java
import java.util.scanner;
```

***Para poder usar la clase scanner necesitamos crear un objeto de ella:***

```java
Scanner scanner = new Scanner(System.in)
```

- ***Con el objeto creado podemos pedir todo tipo de datos:***

```java
int numero = scanner.nextInt();
double decimal = scanner.nextDouble();
String palabra = scanner.nextLine();
boolean valor = scanner.nextBoolean();
byte b = scanner.nextByte();
short s = scanner.nextShort();
long l = scanner.nextLong();
float f = scanner.nextFloat();
```

### Manejo de excepciones:

- ***El uso de Scanner puede generar excepciones. Las mas comunes son:***

```java
// InputMismatchException
//Ocurre cuando el tipo de dato ingresado no coincide con el esperado

try {
    int numero = scanner.nextInt();
} catch (InputMismatchException e) {
    System.out.println("El dato ingresado no es un número válido.");
}

//NoSuchElementException
//Se lanza si intentas leer un dato cuando no hay mas elementos disponibles

// IllegalStateException
//Se lanza si intentas usar un Scanner despues de cerrarlo
```

### Cerrar el Scanner (Buenas Practicas):

- Siempre es una buena practica cerrar el Scanner para liberar recursos

```java
scanner.close();
```
