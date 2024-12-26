***Representan una plantilla o modelo a partir del cual se pueden crear objetos. Las clases encapsulan datos y comportamientos relacionados lo que permite organizar y estructurar el código de manera lógica y reutilizable:***


### Declaración de Clases:

```java
public class Persona {
    // Atributos
    String nombre;
    int edad;

    // Métodos
    public void saludar() {
        System.out.println("¡Hola, mi nombre es " + nombre + "!");
    }
}
```

### Componentes de una Clase:

- ***Atributos:***
	- Variables que representan las propiedades de la clase. Generalmente se declaran como `private` para aplicar el encapsulamiento
- ***Métodos:***
	- Funciones dentro de la clase que definen el comportamiento. Incluyen métodos constructores, getter, setter etc...
- ***Constructores:***
	- Método especial utilizado para inicializar una instancia de un objeto. Tiene el mismo nombre que la clase y no retorna nada:

```java
public class Persona {
    String nombre;

    // Constructor
    public Persona(String nombre) {
        this.nombre = nombre;
    }
}
```

### Modificadores de acceso:

- ***Determinan la visibilidad de los atributos y métodos:***
	- `public` : Accesible desde cualquier lugar
	- `private`: Accesible dentro de la clase
	- `protected` : Accesible dentro del mismo paquete o subclases
	- Sin especificar (paquete): Accesible solo dentro del paquete.

### Instanciar una clase:

- ***Para crear un objeto nuevo usamos la palabra clave `new`:***

```java
Persona persona1 = new Persona("Juan");
persona1.saludar();
```