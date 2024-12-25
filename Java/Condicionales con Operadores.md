### Operador Ternario:

- ***Forma compacta de escribir una condición IF-ELSE***

```java
resultado = (condición) ? valor_si_true : valor_si_false;

int numero = 5;
String resultado = (numero % 2 == 0) ? "Par" : "Impar";
System.out.println(resultado); // Impar
```

### Operadores Lógicos:

- ***Tenemos los siguientes operadores lógicos para los condicionales: && (AND Lógico), || (OR Lógico) y ! (NOT Lógico):***

```java
int edad = 20;
boolean tieneLicencia = true;

if (edad >= 18 && tieneLicencia) {
    System.out.println("Puedes conducir.");
} else {
    System.out.println("No puedes conducir.");
}
```
