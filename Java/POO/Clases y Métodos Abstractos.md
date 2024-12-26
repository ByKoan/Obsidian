***Sirven para definir comportamientos genéricos que las clases derivadas deben implementar***

## Clases Abstractas:

- ***Clase que no se puede instanciar directamente. Se utiliza como una clase base que proporciona una estructura común para sus subclases***

### Características:

- ***Declaración:*** Se definen con la palabra `abstract`

```java
abstract class Animal {
    // Métodos y atributos comunes
}
```

- ***Métodos abstractos:*** Una clase abstracta puede contener métodos abstractos (Sin cuerpo) que las subclases deben implementar

```java
abstract class Animal {
    abstract void makeSound(); // Método abstracto
}
```

- ***Métodos Concretos:*** También puede contener métodos concretos (con implementación)

```java
abstract class Animal {
    void eat() {
        System.out.println("Este animal esta comiendo.");
    }
}
```

- ***Herencia: Una subclase debe implementar todos los métodos abstractos de la clase abstracta, a menos que también sea abstracta. Si no se implementan, la subclase también debe declararse como `abstract`.***

- ***Constructores: Las clases abstractas pueden tener constructores que serán llamados por las subclases al instanciarse***
### Uso:

```java
// Clase 
abstract class Animal {
    abstract void makeSound();
    void eat() {
        System.out.println("Comiendo...");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Woof! Woof!");
    }
}

class Cat extends Animal {
    void makeSound() {
        System.out.println("Meow!");
    }
}
```

```java
// Main

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.makeSound(); // Salida: Woof! Woof!
        myDog.eat();       // Salida: Comiendo...
    }
}
```