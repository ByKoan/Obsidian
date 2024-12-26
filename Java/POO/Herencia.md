***La herencia de una clase permite que una subclase o clase derivada herede los atributos y métodos de la superclase o clase base. Esto promueve la reutilización de código, facilita la extensión de funcionalidades y establece relaciones jerárquicas***

***Utilizamos la palabra clave `extend` para establecer la herencia***

```java
// Superclase
public class Animal {
    String nombre;

    public void comer() {
        System.out.println(nombre + " está comiendo.");
    }
}

// Subclase
public class Perro extends Animal {
    public void ladrar() {
        System.out.println(nombre + " está ladrando.");
    }
}

// Uso
public class Main {
    public static void main(String[] args) {
        Perro perro = new Perro();
        perro.nombre = "Fido";
        perro.comer();  // Heredado de Animal
        perro.ladrar(); // Método propio de Perro
    }
}
```

### Tipos de herencia:

- ***Herencia simple:***
	- Subclase hereda directamente de una sola superclase

```java
public class Vehiculo {
    public void arrancar() {
        System.out.println("El vehículo arranca.");
    }
}

public class Coche extends Vehiculo {
    public void tocarClaxon() {
        System.out.println("El coche toca el claxon.");
    }
}
```

- ***Herencia multinivel:***
	- Una clase puede hereda de otra subclase, formando una jerarquía de herencia

```java
public class Animal {
    public void respirar() {
        System.out.println("El animal está respirando.");
    }
}

public class Mamifero extends Animal {
    public void amamantar() {
        System.out.println("El mamífero amamanta.");
    }
}

public class Perro extends Mamifero {
    public void ladrar() {
        System.out.println("El perro ladra.");
    }
}
```

- ***Herencia múltiple indirecta:***
	- Java no soporta herencia múltiple directa (donde una clase hereda de más de una clase) para evitar conflictos. Sin embargo, se puede lograr utilizando interfaces.

### Acceso a miembros heredados:

- ``public``: Accesible desde cualquier lugar.
- ``protected``: Accesible en la misma clase, subclases y dentro del mismo paquete.
- Sin modificador (paquete): Accesible en clases del mismo paquete.
- ``private``: No accesible directamente en la subclase.

### Uso de la palabra clave `super`:

- ***Llamar al constructor de la superclase***
- ***Acceder a los métodos o atributos de la superclase que han sido sobrescritos***

```java
// Llamar al constructor de la superclase

public class Animal {
    String nombre;

    public Animal(String nombre) {
        this.nombre = nombre;
    }
}

public class Perro extends Animal {
    public Perro(String nombre) {
        super(nombre); // Llamada al constructor de Animal
    }
}

// Llamar a metodos o atributos de la superclase
public class Animal {
    public void hacerSonido() {
        System.out.println("El animal hace un sonido.");
    }
}

public class Perro extends Animal {
    @Override
    public void hacerSonido() {
        super.hacerSonido(); // Llama al método de la superclase
        System.out.println("El perro ladra.");
    }
}
```

### Sobrescritura de métodos `@Override`:

- ***Las subclases pueden modificar el comportamiento de los métodos heredados:***

```java
public class Animal {
    public void hacerSonido() {
        System.out.println("El animal hace un sonido genérico.");
    }
}

public class Gato extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("El gato maúlla.");
    }
}
```

### Clases finales y métodos finales:

- ***Si no deseas que una clase sea heredada puedes declararla con la palabra clave `final`***

```java
public final class Animal {
    // Esta clase no puede ser heredada.
}
```

- ***Los métodos declarados como `final` no pueden ser sobrescritos por las subclases***ç

```java
public class Animal {
    public final void dormir() {
        System.out.println("El animal duerme.");
    }
}
```

### Ejemplo "avanzado":

```java
public class Vehiculo {
    protected int velocidad;

    public void acelerar(int incremento) {
        velocidad += incremento;
        System.out.println("Velocidad: " + velocidad + " km/h");
    }
}

public class Coche extends Vehiculo {
    private int puertas;

    public Coche(int puertas) {
        this.puertas = puertas;
    }

    @Override
    public void acelerar(int incremento) {
        super.acelerar(incremento); // Llamada al método de la superclase
        System.out.println("El coche ha acelerado con éxito.");
    }
}
```
