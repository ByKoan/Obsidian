Véase - https://es.wikipedia.org/wiki/Intel_8086_y_8088

## Registros de propósito general:

### Registro AX:
- Registro acumulador es utilizado para operaciones que impliquen I/O y multiplicaciones y divisiones junto con el DX
### Registro BX:
- Registro base, el único registro de propósito general que puede ser un índice para direccionamiento indexado
### Registro CX: 
- Registro contador, Puede contener un valor para controlar el numero de veces que un ciclo se repite o un valor para corrimiento de bits
### Registro DX:
- Registro de datos, en algunas operaciones se indica mediante este registro el numero de puerto I/O y en las operaciones de multiplicación y división de 16 bits se utiliza junto al AX

## Registros Índice:
### Registro SI:
- Registro índice fuente de 16 bits es requerido por algunas operaciones con cadenas de caracteres. El SI esta asociado con el segmento DS
### Registro DI:
- Registro índice destino también requerido por algunas operaciones con cadenas de caracteres. El DI esta asociado con el segmento ES.

## Registros Apuntadores:
### Registros SP:
- El apuntador de pila de 16 bits esta asociado con el segmento SS y proporciona un valor de desplazamiento que se refiere a la palabra actual que esta siendo procesada en la pila. El sistema maneja de manera automática seste registro aunque el programa se puede hacer ciertas manipulaciones con el
### Registros BP:
- Apuntador de 16 bits facilita referencia de parámetros dentro de la pila

## Registros de bandera (FLAGS):
### OF (Overflow):
- Indica desbordamiento del bit mayor orden después de una operación aritmética de números con signo (1 = existe overflow, 0 = no existe overflow). Para operaciones sin signo no se toma en cuenta esta flag
### DF (Dirección): 
- Controla la selección de incremento o decremento de los registros SI y DI en las operaciones con strings (1 = Decremento automático y 0 = incremento). La bandera DF se controla con las instrucciones STD y CLD
### IF (Interrupción): 
- Controla el trigger de las interrupciones (1 = Habilita las interrupciones y 0 = deshabilita las interrupciones). La interrupción no enmascarable es la única que no puede ser bloqueada por esta bandera. El estado de la bandera IF se controla con las instrucciones STI y CLI
### TF (Trampa): 
- Permite la operación del procesador en modo de depuración (paso a paso)
### SF (Signo): 
- Contiene el signo resultante de una operación aritmética (0 = positivo y 1 = negativo)
### ZF (Cero Flag):
- Indica el resultado de una operación aritmética o de comparación (0 = resultado diferente a 0 y 1 = resultado igual a 0)
### AF (Acarreo Auxiliar): 
- Contiene el acarreo del bit 3. Esta bandera se prueba con las instrucciones DAA y DAS para ajustar el valor de AL después de una suma o resta BCD
### PF (Paridad): 
- Indica si el numero de bits 1, del byte menos significativo de una operación es par (0 = números de bits 1 es impar y 1 = numero de bits 1 es par)
### CF (Acarreo):
- Contiene el acarreo del bit de mayor orden después de una operación aritmética, también almacena el contenido del ultimo bit en una operación de desplazamiento o de rotación

## EIP (Instruction Pointer): 
- Contiene la direccion de memoria donde empieza la siguiente instruccion a ejecutar, a no ser que se produzca un salto o una llamada a subrutina (Funcion)
## Registro de Segmento:
### Registro de CS:
