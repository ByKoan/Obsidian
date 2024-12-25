***Un String es un conjunto de chars en una misma variable***

### Declaración de Strings:

```java
String texto = "Hello World!"
```

### Métodos Comunes de Strings:

- ***Métodos de información sobre el String***

```java
String texto = "Java";
System.out.println(texto.length()); // Nos devuelve la longitud del String

String texto = "";
System.out.println(texto.isEmpty()); // Nos devuelve si esta vacio el string o no
```

- ***Manipulación de Strings***

```java
String texto = "Java";
System.out.println(texto.charAt(1)); // Devuelve el char en la posicion indicada

String texto = "Hola, Java!";
System.out.println(texto.substring(6, 10)); // Nos devuelve los chars que hay entre el rango seleccionado

String saludo = "Hola";
saludo = saludo.concat(", Mundo!");
System.out.println(saludo); // Concatenar (Unir) Strings
```

- ***Comparación de Strings***

```Java
String a = "Java";
String b = "Java";
System.out.println(a.equals(b)); // Compara si son iguales

String a = "Java";
String b = "JAVA";
System.out.println(a.equalsIgnoreCase(b)); // Compara si son iguales ignorando mayusculas y minusculas

String a = "Java";
String b = "JavaScript";
System.out.println(a.compareTo(b)); // Compara una variable con otra si son iguales
```

- ***Transformación de Strings***

```java
String texto = "java";
System.out.println(texto.toUpperCase()); // Convierte el string a mayusculas

String texto = "JAVA";
System.out.println(texto.toLowerCase()); // Convierte el string a misculas

String texto = "   Hola, Java!   ";
System.out.println(texto.trim()); // Elimina los espacios al principio y al final
```

- ***Búsqueda de Strings***

```java
String texto = "Hola, Java!";
System.out.println(texto.indexOf("Java")); // Devuelve la posicion de la primera letra encontrada

String texto = "Java es Java";
System.out.println(texto.lastIndexOf("Java")); // Devuelve la posicion de la ultima letra encontrada

String texto = "Hola, Java!";
System.out.println(texto.contains("Java")); // Compara si el string contiene lo que buscamos
```

- ***Remplazo en Strings***

```java
String texto = "Java";
System.out.println(texto.replace('a', 'o')); // Remplazar x letra por otra letra
```

- ***División de Strings***

```java
String texto = "uno,dos,tres";
String[] partes = texto.split(",");
System.out.println(Arrays.toString(partes)); // Separa el string en un array con el delimitador que le indiquemos
```

