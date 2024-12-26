***El condicional `IF` es como en todos los lenguajes se ejecuta un código especifico si se da un a condición:***

```java
if (condición) {
    // Código a ejecutar si la condición es verdadera
}
```

### IF-ELSE:

- ***El bloque ``ELSE`` se ejecutara si la primera condición no se ha dado:***ç

```java
if (condición) {
    // Código si la condición es verdadera
} else {
    // Código si la condición es falsa
}
```

### IF-ELSE IF-ELSE:

- ***Utilizado cuando queremos que haya mas de una condición:***

```java
if (condición1) {
    // Código si la condición1 es verdadera
} else if (condición2) {
    // Código si la condición2 es verdadera
} else {
    // Código si ninguna condición anterior es verdadera
}
```

### IF Anidados:

- ***Se pueden anidar IF dentro de otros IF para manejar escenarios complejos:***

```java
int edad = 20;
boolean tieneLicencia = true;

if (edad >= 18) {
    if (tieneLicencia) {
        System.out.println("Puedes conducir.");
    } else {
        System.out.println("Necesitas una licencia para conducir.");
    }
} else {
    System.out.println("No tienes la edad suficiente para conducir.");
}
```