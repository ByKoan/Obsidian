***Forma de organizar clases e interfaces en grupos lógicos. Ayudan a evitar conflictos de nombres, mejoran la estructura y legibilidad del código y facilitan la gestión de proyectos grandes***

### Tipos de paquetes:

- ***Paquetes incorporados:*** (Built-in package) Java proporciona una colección de paquetes predefinidos:
	- java.lang (Clases básicas como ``String`` ``Math`` ``Objetc`` etc.)
	- java.util (Colecciones, fechas, etc.)
	- java.io (Entrada/Salida)
	- java.net (Redes)
	- javax.swing (Diseño de interfaces graficas)

- ***Paquetes personalizados:*** (user-definied package) Paquetes creados por el desarrollador para organizar el código según las necesidades especificas

### Creación de Paquetes:

- Se guardaría el archivo como - `com/ejemplo/miapp/MiClase.java`

```java
// Crear un paquete llamado "com.ejemplo.miapp"
package com.ejemplo.miapp;

public class MiClase {
    public void mostrarMensaje() {
        System.out.println("Hola desde el paquete com.ejemplo.miapp");
    }
}
```

### Usar Paquetes:

```java
import com.ejemplo.miapp.MiClase;

public class Main {
    public static void main(String[] args) {
        MiClase obj = new MiClase();
        obj.mostrarMensaje();
    }
}

// Si queremos importar todo - import com.ejemplo.miapp.*;
```

### Subpaquetes: 

- ***Los paquetes al igual que las clases pueden contener Subpaquetes para organizar aun mas el código:***

```java
package com.ejemplo.utilidades;

// Se almacena como com/ejemplo/utilidades
```