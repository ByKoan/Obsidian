### Clases internas:

- ***Definidas dentro de otra clase. Se utiliza principalmente para agrupar lógica que esta fuertemente relacionada con la clase que las contiene***
#### Clases anidadas estáticas:

- ***Clases internas que se declaran con el modificador `static`***
- ***No tienen acceso directo a los miembros no estáticos de la clase externa.***
- ***Se comportan como una clase independiente dentro de otra clase.***

```java
class Outer {
    static class StaticNested {
        void display() {
            System.out.println("Soy una clase anidada estática.");
        }
    }
}
```

```java
Outer.StaticNested nested = new Outer.StaticNested();
nested.display();
```

#### Clases internas no estáticas:

- ***Tienen acceso directo a los miembros (incluidos los privados) de la clase externa***
- ***Requieren una instancia de la clase externa para ser creadas***

```java
class Outer {
    class Inner {
        void display() {
            System.out.println("Soy una clase interna no estática.");
        }
    }
}
```

```java
Outer outer = new Outer();
Outer.Inner inner = outer.new Inner();
inner.display();
```

#### Clases Locales:

- ***Se definen dentro de un método o un bloque de código:***
- ***Solo disponibles dentro del método o bloque donde fueron declaradas***
- ***Pueden acceder a las variables locales del método siempre que sean `final` o efectivamente finales.***

```java
class Outer {
    void display() {
        class Local {
            void showMessage() {
                System.out.println("Soy una clase interna local.");
            }
        }
        Local local = new Local();
        local.showMessage();
    }
}
```

```java
Outer outer = new Outer();
outer.display();
```

#### Clases Anónimas:

- ***Una forma especial de clases internas que no tienen nombre***
- ***Se crean como instancias directas de una clase o una interfaz***
- ***Se utilizan comúnmente para implementar interfaces o extender clases abstractas de manera rápida.***
### Clases estáticas:

- ***Clase declarada dentro de otra clase usando la palabra clave `static`. Estas clases no tienen una referencia implícita a una instancia de la clase contenedora lo que las diferencia de las clases internas no estáticas***

```java
class OuterClass {
    static class StaticNestedClass {
        void nestedMethod() {
            System.out.println("Método de la clase estática anidada");
        }
    }
}
```


```java
public class Main {
    public static void main(String[] args) {
        // No se necesita instancia de OuterClass
        OuterClass.StaticNestedClass nested = new OuterClass.StaticNestedClass();
        nested.nestedMethod();
    }
}
```
### Clases finales:

- ***Son clases que no pueden ser heredadas. Útil para prevenir modificaciones no deseadas en el comportamiento de una clase, asegurando que su implementación permanezca constante. Aquí tienes todo lo especial sobre las clases finales:***

```java
final class MiClaseFinal {
    public void mostrarMensaje() {
        System.out.println("Esto es una clase final.");
    }
}
```

- ***Instanciar las clases finales:***

```java
MiClaseFinal obj = new MiClaseFinal();
```