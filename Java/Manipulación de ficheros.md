- ***Para la manipulación de ficheros tenemos 2 clases principales:***

### JAVA.IO:

- **`File`**: Representa un fichero o un directorio. Proporciona métodos para crear, eliminar, renombrar y consultar propiedades de los ficheros/directorios.
- **`FileReader` y `FileWriter`**: Se usan para leer y escribir texto en ficheros.
- **`BufferedReader` y `BufferedWriter`**: Proporcionan una manera eficiente de leer y escribir texto con búferes.
- **`FileInputStream` y `FileOutputStream`**: Para leer y escribir datos en formato binario.

### JAVA.NIO.FILE:

- **`Files`**: Contiene métodos para operaciones de alto nivel como copiar, mover, y leer/escribir líneas de texto.
- **`Path` y `Paths`**: Representan rutas de ficheros de manera flexible y manejable.
- **`FileSystems`**: Permite interactuar con sistemas de ficheros subyacentes.

### Creación de Ficheros:

```java
import java.io.File;
import java.io.IOException;

public class CrearFichero {
    public static void main(String[] args) {
        try {
            File fichero = new File("archivo.txt");
            if (fichero.createNewFile()) {
                System.out.println("Fichero creado: " + fichero.getName());
            } else {
                System.out.println("El fichero ya existe.");
            }
        } catch (IOException e) {
            System.out.println("Ocurrió un error.");
            e.printStackTrace();
        }
    }
}
```

### Escribir en Ficheros:

```java
import java.io.FileWriter;
import java.io.IOException;

public class EscribirFichero {
    public static void main(String[] args) {
        try {
            FileWriter escritor = new FileWriter("archivo.txt");
            escritor.write("Hola, mundo!");
            escritor.close();
            System.out.println("Se ha escrito en el fichero.");
        } catch (IOException e) {
            System.out.println("Ocurrió un error.");
            e.printStackTrace();
        }
    }
}
```

### Leer Ficheros:

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class LeerFichero {
    public static void main(String[] args) {
        try {
            File fichero = new File("archivo.txt");
            Scanner lector = new Scanner(fichero);
            while (lector.hasNextLine()) {
                String linea = lector.nextLine();
                System.out.println(linea);
            }
            lector.close();
        } catch (FileNotFoundException e) {
            System.out.println("El fichero no fue encontrado.");
            e.printStackTrace();
        }
    }
}
```

### Eliminar Ficheros:

```java
import java.io.File;

public class EliminarFichero {
    public static void main(String[] args) {
        File fichero = new File("archivo.txt");
        if (fichero.delete()) {
            System.out.println("Fichero eliminado: " + fichero.getName());
        } else {
            System.out.println("No se pudo eliminar el fichero.");
        }
    }
}
```

### Copiar ficheros:

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;

public class CopiarFichero {
    public static void main(String[] args) {
        Path origen = Paths.get("archivo.txt");
        Path destino = Paths.get("archivo_copia.txt");
        try {
            Files.copy(origen, destino);
            System.out.println("Fichero copiado exitosamente.");
        } catch (IOException e) {
            System.out.println("Error al copiar el fichero.");
            e.printStackTrace();
        }
    }
}
```

### Mover un fichero:

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;

public class MoverFichero {
    public static void main(String[] args) {
        Path origen = Paths.get("archivo.txt");
        Path destino = Paths.get("nueva_carpeta/archivo.txt");
        try {
            Files.move(origen, destino);
            System.out.println("Fichero movido exitosamente.");
        } catch (IOException e) {
            System.out.println("Error al mover el fichero.");
            e.printStackTrace();
        }
    }
}
```

### Lectura de binarios:

```java
import java.io.FileInputStream;
import java.io.IOException;

public class LeerBinario {
    public static void main(String[] args) {
        try (FileInputStream fis = new FileInputStream("archivo.bin")) {
            int byteLeido;
            while ((byteLeido = fis.read()) != -1) {
                System.out.print((char) byteLeido);
            }
        } catch (IOException e) {
            System.out.println("Error al leer el fichero.");
            e.printStackTrace();
        }
    }
}
```