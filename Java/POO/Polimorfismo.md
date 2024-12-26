***El término proviene del griego y significa "muchas formas". Permite que una entidad, como un método o una referencia de objeto pueda comportarse de diferentes maneras según como se utiliza:***

### Tipos de Polimorfismo:

- ***Polimorfismo en tiempo de compilación (Sobrecarga de métodos):***
	- También llamado *Static binding*
	- Ocurre cuando dos o mas métodos en la misma clase tienen el mismo nombre pero de diferentes listas de parámetros (por tipo, cantidad o ambas)
	- La resolución del método se realiza durante la compilación

```java
class Calculadora {
    int sumar(int a, int b) {
        return a + b;
    }

    double sumar(double a, double b) {
        return a + b;
    }

    int sumar(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculadora calc = new Calculadora();
        System.out.println(calc.sumar(2, 3));           // Llama a sumar(int, int)
        System.out.println(calc.sumar(2.5, 3.5));      // Llama a sumar(double, double)
        System.out.println(calc.sumar(1, 2, 3));       // Llama a sumar(int, int, int)
    }
}
```

- ***Polimorfismo en tiempo de ejecución (Sobrescritura de métodos):*** 
	- También llamado *dynamic binding*
	- Se da cuando una clase hija redefine un método de una clase padre
	- La selección del método se realiza en tiempo de ejecución dependiendo del objeto al que apunte la referencia

```java
class Animal {
    void hacerSonido() {
        System.out.println("El animal hace un sonido");
    }
}

class Perro extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("El perro ladra");
    }
}

class Gato extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("El gato maúlla");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal miAnimal;

        miAnimal = new Perro();
        miAnimal.hacerSonido();  // Salida: El perro ladra

        miAnimal = new Gato();
        miAnimal.hacerSonido();  // Salida: El gato maúlla
    }
}
```

### Características del Polimorfismo:

- ***Uso de referencias genéricas: Puedes usar una referencia del tipo de la clase base para apuntar a objetos de subclases***

```java
Animal animal = new Perro();  // Referencia de tipo Animal apuntando a un objeto de tipo Perro.
```

- ***Permite la extensibilidad: Puedes añadir nuevas clases o tipos al programa sin modificar el código existente.***

- ***Promueve el diseño basado en [[Interfazes]]: El polimorfismo es crucial cuando trabajas con interfaces y clases abstractas***

```java
interface Figura {
    void dibujar();
}

class Circulo implements Figura {
    public void dibujar() {
        System.out.println("Dibujando un círculo");
    }
}

class Cuadrado implements Figura {
    public void dibujar() {
        System.out.println("Dibujando un cuadrado");
    }
}

public class Main {
    public static void main(String[] args) {
        Figura figura;

        figura = new Circulo();
        figura.dibujar();  // Salida: Dibujando un círculo

        figura = new Cuadrado();
        figura.dibujar();  // Salida: Dibujando un cuadrado
    }
}
```

### Reglas Importantes:
#### Para la Sobrescritura de métodos:

- El método debe tener el mismo nombre, parámetros y tipo de retorno
- Debe tener la misma o mayor visibilidad 
- El método en la clase debe ser accesible para que se pueda ver sobrescrito
- Si el método en la clase base es `final` o `static` no podrá ser sobrescrito

#### Para la sobrecarga de métodos:

- Los métodos pueden diferir en el numero y/o tipo de parámetros
- No depende del tipo de retorno; no puedes sobrecargar un método cambiando solo su tipo de retorno

#### Ejemplo completo con polimorfismo:

```java
abstract class Empleado {
    String nombre;

    Empleado(String nombre) {
        this.nombre = nombre;
    }

    abstract void trabajar();
}

class Ingeniero extends Empleado {
    Ingeniero(String nombre) {
        super(nombre);
    }

    @Override
    void trabajar() {
        System.out.println(nombre + " está diseñando un sistema.");
    }
}

class Gerente extends Empleado {
    Gerente(String nombre) {
        super(nombre);
    }

    @Override
    void trabajar() {
        System.out.println(nombre + " está gestionando el equipo.");
    }
}

public class Main {
    public static void main(String[] args) {
        Empleado e1 = new Ingeniero("Alice");
        Empleado e2 = new Gerente("Bob");

        e1.trabajar();  // Salida: Alice está diseñando un sistema.
        e2.trabajar();  // Salida: Bob está gestionando el equipo.
    }
}
```