Vea [[Bucle_While]], [[Condicionales]], [[Variables]], [[Tipos_de_datos]]

Los bucles ``For``, otro tipo de bucles al igual que el [[Bucle_While]] que busca que se cumpla una o varias condiciones.

La sintaxis es la siguiente:
```c
for (
	tipo_de_dato variable_local1 = valor1, variable_local2 = valor2, ...; 
	condicion; 
	incrementador1, incrementador2, ...
) {

}
```

Ejemplos:
```c
for (int i = 0, j = 1; i < 10 && j > 20; i++, j += 2)
```

```c
for (
	int i = 0, j = 1, x = 20; 
	(i < 10 && j > 20) || (x > j && j > i); 
	i++, j += 2, x = j + 1
)
```


El bucle ``For`` funciona de la siguiente manera, se llama a la función, se abre los paréntesis, y empezaremos con la primera [[Condicionales|condicion]], normalmente se suele crear una [[Variables|variable]] "``i``" [[Tipos_de_datos|tipo]] ``int`` en el bucle pero puedes comparar otras que ya tengas creadas fuera del bucle de todos los [[Tipos_de_datos|tipos]], lo separamos de la segunda [[Condicionales|condición]] mediante "``;``" y por ultimo faltaría la parte que hace que esas condiciones se cumplan. 

Un ejemplo:
```c
#include <stdio.h>

int main () {
	int a = 1, b = 5;
	
	for (; a < b; a++) {
		printf("%d", a);
	}
	return 0;

}
```

Lo que haría este programa seria ir comprobando que "``a``" es menor que "``b``" y sumar 1 hasta que sean iguales.