***Permiten definir un contrato o conjunto de métodos que una clase debe implementar. Fundamentales para construir aplicaciones modulares, escalables y que sigan el principio de programación orientada a interfaces***

### Características de las interfaces:
- ***Definición de un contrato:***
	- Una interfaz define un conjunto de métodos abstractos que las clases que las implementan deben proporcionar
	- Las interfaces no pueden contener implementación concreta
- ***Modificadores predeterminados:***
	- Los métodos en una interfaz son `public` y `abstract` por defecto no es necesario especificarlo
	- Las variables son  `public static final` por defecto
- ***Compatibilidad con múltiples implementación:***
	- Una clase puede implementar múltiples interfaces, lo que permite superar las limitaciones de la herencia única de Java
- ***Otras características:***
	- Desde java 8, las interfaces pueden tener métodos con implementación predeterminada (métodos `default`) los métodos estáticos `static` también son permitidos
	- Desde java 9, las interfaces pueden incluir métodos privados para encapsular la lógica común entre métodos `default` o `static`

### Declaración básica de una interfaz:

```java
// Definición de una interfaz
public interface Animal {
    // Método abstracto
    void hacerSonido();

    // Método con implementación predeterminada (Java 8+)
    default void dormir() {
        System.out.println("El animal está durmiendo.");
    }

    // Método estático
    static void descripcion() {
        System.out.println("Todos los animales tienen vida.");
    }
}
```

### Implementación de una Interfaz:

```java
// Clase que implementa la interfaz
public class Perro implements Animal {

    // Implementación del método abstracto
    @Override
    public void hacerSonido() {
        System.out.println("Guau Guau");
    }
}
```

### Uso:

```java
public class Main {
    public static void main(String[] args) {
        Perro perro = new Perro();
        perro.hacerSonido(); // Salida: Guau Guau
        perro.dormir();      // Salida: El animal está durmiendo.

        // Llamada al método estático
        Animal.descripcion(); // Salida: Todos los animales tienen vida.
    }
}
```

### Ejemplo "avanzado":

```java
public interface Volador {
    void volar();
}

public interface Nadador {
    void nadar();
}

public class Pato implements Volador, Nadador {
    @Override
    public void volar() {
        System.out.println("El pato está volando.");
    }

    @Override
    public void nadar() {
        System.out.println("El pato está nadando.");
    }
}
```

