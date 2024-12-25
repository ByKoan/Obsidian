### Conversiones de otros tipos a Strings:
- ***Cualquier tipo de dato puede convertirse en un String utilizando diversos métodos:***

```java
// String.valueOf()

int numero = 42;
String texto = String.valueOf(numero);
System.out.println(texto); // Tipos INT, DOUBLE, BOOLEAN ETC...
```

```JAVA
// Concatenacion con el operador +

int numero = 42;
String texto = "El numero es: " + numero;
System.out.println(texto);
```

```java
// Metodo de la clase String toString()

class Persona {
    String nombre;
    Persona(String nombre) {
        this.nombre = nombre;
    }
    @Override
    public String toString() {
        return "Nombre: " + nombre;
    }
}

Persona p = new Persona("Juan");
System.out.println(p.toString()); // "Nombre: Juan"
```

### Conversión de Strings a otros tipos:
- ***Se pueden convertir un String en otros tipos de datos usando diversas clases y métodos***

```java
//Tipos numericos

String texto = "42";
int numero = Integer.parseInt(texto);
System.out.println(numero); // 42

String texto = "42.5";
double numero = Double.parseDouble(texto);
System.out.println(numero); // 42.5

String textoLargo = "123456789";
long numeroLargo = Long.parseLong(textoLargo);
System.out.println(numeroLargo); // 123456789
```

```java
// Convertir a valores booleanos

String texto = "true";
boolean valor = Boolean.parseBoolean(texto);
System.out.println(valor); // true
```

```java
// Conversion a Chars

String texto = "A";
char caracter = texto.charAt(0);
System.out.println(caracter); // 'A'
```