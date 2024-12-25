***La mayoría de variables en Java se declaran como en C:***

```python
tipo nombreVariable;

int numero;
```

- ***Si creamos una variable pero no la inicializamos nos dará errores, por lo que hay que asignarla un valor en algún momento:***

```java
int numero = 1;
String texto = "Hello World!"
```

***Reglas de variables en Java:***
- ***Deben comenzar con una letra, símbolo de dólar o un guion bajo***
- ***No pueden comenzar con un numero***
- ***No puedes usar palabras reservadas como `int` `class` etc.***
- ***Son case-sensitive (`edad` y `Edad` son diferentes variables)***

### Tipos de Variables:

- ***Locales: declaradas dentro de un método o bloque y accesibles desde el mismo***
- ***De instancia: Definidas fueras de métodos y no tienen el modificador static, Pertenecen a una instancia especifica de la clase***
- ***Estáticas o de clase: definidas con el modificador ``static``. Comparten el mismo valor para todas las instancias de la clase***
- ***Constantes: "variables" que no varían su valor en todo el programa, indicador `final`***

### Tipos de Datos:

- ***Como bien hemos hablado antes Java se parece mucho a C por lo que contiene los tipos de datos primitivos:***

| Tipo    | Tamaño  | Valor Predeterminado | Rango            | Ejemplo              |
| ------- | ------- | -------------------- | ---------------- | -------------------- |
| byte    | 8 Bits  | 0                    | -128 a 127       | byte b = 100;        |
| short   | 16 Bits | 0                    | -32,768 a 32,767 | short s = 1000;      |
| int     | 32 Bits | 0                    | -2^31 a 2^31 -1  | int i = 12345;       |
| long    | 64 Bits | 0L                   | -2^63 a 2^63 -1  | long l = 123456789l  |
| float   | 32 Bits | 0.0f                 | Aprox +3.4e38    | float f = 3.14f;     |
| double  | 64 Bits | 0.0d                 | Aprox +1.8e308   | double d = 3.14159;  |
| char    | 16 Bits | \u0000               | 0 a 65,535       | char c = 'A';        |
| boolean | 1 Bit   | false                | true o false     | boolean flag = true; |
### Tipos de Datos no Primitivos:

- ***Igual que tenemos datos primitivos, tenemos datos no primitivos como Strings, Arrays y Clases y objetos, los veremos mas adelante***

### Conversión de Tipos de Datos (Casting):

- ***Existen dos formas de convertir datos, Conversión implícita:***

```java
int numero = 10;
double resultado = numero; // Conversión implícita de int a double
```

- ***Conversión Explicita (Casting):***

```java
double valor = 9.8;
int entero = (int) valor; // Conversión explícita de double a int
```

### Modificadores de Acceso para Variables:

- ***`private`: Solo accesible dentro de la misma clase***
- ***`default` Accesible dentro del mismo paquete***
- ***`protected` Accesible dentro del paquete y por subclases***
- ***`public` Accesible desde cualquier lugar***
