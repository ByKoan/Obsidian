
- Función de 64 bits (**unsigned64_t**)
- Presente en todos los CPUs después del Pentium II
- Cuenta el numero de ticks desde que se inicio el CPU
- Suele incrementarse dependiendo de varias frecuencias 
### Sintaxis (Func en C):

```c
static inline uint64_t rdtsc() { // Instruccion RDTSC (Cuenta los ticks del CPU en ASM)
    unsigned int lo, hi; // Variables Low y High que guardaremos los valores del registro EAX y EDX
    __asm__ volatile ("rdtsc" : "=a" (lo), "=d" (hi));
    return ((uint64_t)hi << 32) | lo; // Retornamos los 2 valores juntos como 1 de 64 bits
    /*
     *
     * a = 0xA = 1010
     * al desplazarlos en 8 se queda como 1010 0000 0000
     * 0xff 0 1111 1111 
     * 1010 0000 0000 + 1111 1111 = 1010 1111 1111
     * 
     */
}
```


### Usos:
- Obtener tiempo activo de la CPU
- Obtener semilla para generación de semilla de números pseudoaleatorios
- Obtener tiempo de ejecución de un fragmento de código
- Se podrá utilizar también para métodos en malware como saber si nuestro código esta corriendo en un equipo virtualizado
- En determinados CPU puedes saber la velocidad de los núcleos, en los actuales puedes saber la velocidad base

***Buscar Info***
