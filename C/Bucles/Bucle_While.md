Vea [[Bucles_For]], [[Condicionales]], [[Variables]], [[Tipos_de_datos]], [Bucles while](https://learn.microsoft.com/es-es/cpp/c-language/while-statement-c?view=msvc-170)

En C tenemos varios tipos de bucles, uno de ellos es "``while``"
Funciona de la siguiente manera: 
Si la [[Condicionales|condición]] que le hemos marcado es verdadera o la que nosotros hayamos comparado, se ejecutara esa parte del código, si no lo es se repetirá hasta que lo sea.

![[Pasted image 20240909120631.png|304x340]]

Un ejemplo de como funciona el bucle "``while``" :

```c
#include <stdio.h>

int main () {
     int num = 5;
     int num2 = 1;

     while(num > num2) {
          printf("Hello World!");
     }
}
```
