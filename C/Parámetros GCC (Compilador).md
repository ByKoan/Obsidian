### Parámetros básicos:

- gcc "archivo".c
- gcc archivo.c -o archivo

### Parámetros de optimización

- ``-O0`` (Sin optimización) por defecto
- ``-O1``, ``-O2`` y ``-O3`` Optimización del código, cuanto mayor es el numero mas agresiva será la optimización
- ``-Os`` Optimización para reducir el tamaño del ejecutable
- ``-Ofast`` Habilita todas las optimizaciones de nivel -O3 y otras optimizaciones que pueden cambiar el comportamiento del programa (Por ejemplo permite instrucciones que violan los estándares del lenguaje)

### Parámetros de depuración:

- `-g` Genera información de depuración. Útil si estas utilizando herramientas como `gdb` para depurar
- `-ggdb` Genera información de depuración especifica para `gdb`

### Parámetros de advertencia:
- `-Wall`  Activa la mayoría de las advertencias estándar. Muy útil para detectar problemas potenciales en el código.
- `-Werror`  Trata las advertencias como errores. Esto hará que la compilación falle si hay advertencias.
- `-Wextra`  Activa advertencias adicionales que no están habilitadas por `-Wall`.
- `-Wno-<warning>`  Desactiva una advertencia específica. Por ejemplo, `-Wno-unused-variable` desactiva la advertencia sobre variables no usadas.

### Parámetros de enlace:

- `-l<nombre_biblioteca>`  Enlaza con una biblioteca específica. Por ejemplo, `-lm` enlaza con la biblioteca matemática.
- `-L<directorio>`  Añade un directorio de búsqueda de bibliotecas al enlazar.
- `-static`  Genera un ejecutable estático, lo que significa que se incluyen todas las bibliotecas necesarias dentro del archivo ejecutable.
- `-shared`  Genera una biblioteca compartida (en lugar de un ejecutable).

### Parámetros de preprocesador:

- `-D<nombre>`  Define una macro durante la compilación. Ejemplo: `-DDEBUG` define la macro `DEBUG`.
- `-U<nombre>`  Desdefine una macro.
- `-I<directorio>`  Añade un directorio al listado de directorios donde buscar archivos de cabecera (`.h`).
- `-include <archivo.h>`  Incluye un archivo de cabecera antes de procesar cualquier archivo fuente.
- `-imacros <archivo>`  Procesa un archivo como si fueran macros antes de compilar cualquier archivo fuente.

### Parámetros de salida:

- `-S`  Genera un archivo ensamblador (`archivo.s`) en lugar de compilar directamente a código de máquina.
- `-E`  Ejecuta solo el preprocesador, generando el archivo con la expansión de macros.
- `-c`  Compila los archivos fuente en objetos `.o` sin enlazarlos en un ejecutable.

### Parámetro de arquitectura:

- `-m32`  Compila el programa en 32 bits.
- `-m64`  Compila el programa en 64 bits.
- `-march=<arquitectura>`  Optimiza el código para una arquitectura específica, como `x86-64` o `arm`.

### Parámetros para controlar la salida:

- `-v`  Muestra información detallada sobre el proceso de compilación.
- `-Q`  Muestra información adicional sobre las opciones activadas durante la compilación.

### Parámetros de idioma:

- `-std=c99`  Utiliza la versión del estándar de C especificada, como `c99`, `c11`, `gnu99`, etc.
- `-ansi`  Activa el modo estricto ANSI, desactivando extensiones de GCC.

### Parámetros avanzados:

- `-fPIC`  Genera código independiente de posición (usado generalmente para bibliotecas compartidas).
- `-fno-exceptions`  Desactiva las excepciones (para C++).
- `-fno-rtti`  Desactiva la información de tipo de tiempo de ejecución (también para C++).

### Parámetros de inclusión y exclusión:
- `-x <lenguaje>`  Fuerza el tipo de lenguaje del archivo fuente, por ejemplo, `-x c` para forzar que un archivo sea tratado como C, aunque tenga una extensión diferente.