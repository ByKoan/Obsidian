C nos proporciona varias funciones y valores para poder trabajar con archivos
### Trabajando con archivos es ¡¡¡ MUY IMPORTANTE !!! comprobar que todo haya sido realizado correctamente y no haya fallado nada

### ``fopen``

- La función *"fopen"* sirve para poder abrir un archivo:

Sintaxis:

```c
fopen("archivo.txt", "wb");
```

### ``fclose``

- La función *"fclose"* sirve para poder cerrar el archivo anteriormente usado.

Sintaxis: 

```c
fclose(archivo);
```
### ``fread``

- La función *"fread"* sirve para poder leer archivos 

Sintaxis: 

```c
fread(
        buffer_read,  
        sizeof(char),   
        sizeof(buffer_write)/sizeof(char), 
        archivo
    );
```

### ``fwrite``

- La función *"fwrite"* sirve para escribir en archivos

Sintaxis:

```c
fwrite(
        buffer_write,                      // Bufer
        sizeof(char),                      // _ElementSize 
        sizeof(buffer_write)/sizeof(char), // _ElementCount 
        archivo                            // _Stream
    );
```


Hay varios modos de apertura:
