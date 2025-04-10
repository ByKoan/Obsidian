- El **IA32** (**Intel 386** y posteriores) son arquitecturas de 32 bits, es decir, tiene la memoria asignada en 2^32 con palabras de 8 bits (1 Byte). 

- Cada uno de estos bytes se ocupa de una posición de la memoria del 0 hasta el 2^32 
- Como 2^32 son exactamente 4 gigabytes de memoria el **IA32** puede gestionar hasta 4 Gigabytes de memoria

- Al ser una arquitectura de **32bits** cuando lee o escribe memoria siempre lo hace en direcciones que son múltiples de **4** y siempre lee o escribe 4 bytes **(32 bits)** 

### Como se guardan los datos en memoria: 
- Las instrucciones y los datos se guardaran en la memoria, los datos si son números naturales se guardaran en binario, si son caracteres se guardara su valor en **ASCII** 
- Si son números enteros con signo se guardan en complemento a 2