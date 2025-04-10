***En java aparte de los métodos que vimos en [[Manipulación de ficheros]] tenemos un par de clases para crear, escribir y leer archivos***

### Leer archivos:
- ***Clase `BufferedReader`:***

```java
import java.io.*;

public class LeerFichero {
    public static void main(String[] args) {
        try {
            File fichero = new File("ruta_del_fichero.txt");
            FileReader fr = new FileReader(fichero);
            BufferedReader br = new BufferedReader(fr); 
            // Instanciar las clases con la que leeremos

            String linea;
            while ((linea = br.readLine()) != null) {
                System.out.println(linea);
            }

            br.close();
            fr.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Escribir archivos:
- ***Clase `BufferedWriter`:***

```java
import java.io.*;

public class EscribirFichero {
    public static void main(String[] args) {
        try {
            File fichero = new File("ruta_del_fichero.txt");
            FileWriter fw = new FileWriter(fichero);
            BufferedWriter bw = new BufferedWriter(fw);
            // Instanciamos las clases con la que escribiremos

            bw.write("Primera línea de texto.");
            bw.newLine();
            bw.write("Segunda línea de texto.");
            bw.newLine();

            bw.close();
            fw.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```