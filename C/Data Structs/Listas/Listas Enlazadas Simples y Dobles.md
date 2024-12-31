
### Listas enlazadas simples:
Una lista enlazada simple es una [[Estructuras|estructura]] de datos que consiste en una secuencia de nodos, donde cada nodo contiene dos partes:

```c
typedef struct Node  {
	struct Node* NextNode;
	int Num; 
} Node; 
```

1. **``Dato``**: El valor o información que se almacena en ese nodo.
2. **``Enlace o puntero``**: Una referencia al siguiente nodo en la secuencia.

La característica principal de una lista enlazada simple es que cada nodo está conectado solo al nodo siguiente, formando una cadena unidireccional. El primer nodo de la lista se llama **cabeza** (``head``), y el último nodo tiene un enlace que apunta a `NULL` o `nulo`, indicando el final de la lista.

Un ejemplo básico en código de una lista enlazada:

Consiste en crear una [[Estructuras|estructura]], la cual mediante funciones reservaremos memoria y iremos creando los nodos añadiendo los valores

```c
#include <stdio.h>
#include <stdint.h>
#include <stdlib.h>
#include <string.h>

typedef struct Node // Declaramos la estructura
	{
		struct Node* NextNode; // Puntero a siguiente nodo
		int Num; // Variable la cual usaremos para añadir los nums
	}Node; 
	 

Node* init_list (); // Funcion que inicia la lista
Node* push (Node* init); // Funcion que agrega los nums
void print_list (Node* init); // Funcion que imprime la lista
Node* free_mem (Node* init);

int main () {
	
	Node* ptr_node = init_list(); // LLamamos a la funcion para iniciar la lista y guardamos el ptr en ptr_node que sera el primer nodo
	ptr_node -> Num = 10; // Añadimos el primer valor un 10
	Node* LastNode = push(ptr_node); // Llamamos a la funcion push para crear el siguiente node y que podamos agregar el siguiente valor
	LastNode -> Num = 20; // Añadimos el primer valor un 20
	LastNode = push(ptr_node); // Llamamos a la funcion push para crear el ultimo y que podamos agregar el siguiente valor
	LastNode -> Num = 30; // Añadimos el primer valor un 30

	print_list(ptr_node); // Imprimimos la lista

	free_mem(ptr_node); // Liberamos la memoria reservada

	return 0;
}

Node* init_list () {  // Funcion que inicia la lista 

	Node* ptr_mem = malloc(sizeof(Node)); // Reservamos memoria en funcion de lo que ocupa el nodo
	memset(ptr_mem, 0, sizeof(Node)); // Ponemos esa memoria a 0

	return ptr_mem; // Retornamos el puntero con la memoria reservada
}

Node* push (Node* init) {  // Funcion para agregar valores 

	for (Node* now = init; now != NULL; now = now -> NextNode) {  // Creamos la variable now que sera el nodo presente (el primero), si now es diferente a null pasa al siguiente nodo.
		if (now -> NextNode == NULL){ // Si el siguiente node es = a NULL que cree uno nuevo mediante la funcion de iniciar la lista
			now -> NextNode = init_list();
			return now -> NextNode; // Retornamos el siguiente node
		}
	}

}

void print_list (Node* init) {  // Funcion imprimir la lista

	for (Node* now = init; now != NULL; now = now -> NextNode) { // Creamos la variable now que sera el nodo presente (el primero), si now es diferente a null pasa al siguiente nodo.
		printf("El valor de memoria es : %p -> %d\n", now, now -> Num); // Imprime la direccion de memoria de now
	}

}

Node* free_mem (Node* init) {
	Node* ptr_saved = NULL;
	for (Node* now = init; now != NULL;) { // Creamos la variable now que sera el nodo presente (el primero), si now es diferente a null pasa al siguiente nodo.

		ptr_saved = now -> NextNode;  // Guardamos el siguiente node en este ptr 

		printf("Liberando node... %p\n", now);

		free(now);  // Liberamos la memoria
		
		now = ptr_saved;  // Guardamos el node presente en ptr_saved

	}
	
}
```

### Listas enlazadas dobles
Una lista enlazada doble consiste en una secuencia de nodos formados por una [[Estructuras|estructura]] de datos igual que las _listas enlazadas simples_ pero con la diferencia que cada nodo esta comunicado con el **anterior y el siguiente**, en las listas dobles cada nodo contiene un elemento mas :

```c
typedef struct Nodes { 
    uint8_t dato;  
    struct Nodes * NextNode;
    struct Nodes * LastNode;
} Nodes ;
```

1. **``Dato``**: El valor o información que se almacena en ese nodo.
2. **``Enlace o ``[[Punteros|puntero]]`` al siguiente``**: Una referencia al siguiente nodo en la secuencia.
3. **``Enlace o puntero al anterior``**: Una referencia al nodo anterior en la secuencia.

Un ejemplo básico en código de una _lista enlazada doble_:

Tiene varias funciones las cuales consisten en, crear la lista inicial, crear el siguiente nodo, eliminar nodos, liberar memoria y imprimir los nodos.

``code.c``:
```c
#ifndef __CODE_C__
#define __CODE_C__
#include "code.h"

Nodes *InitList () { // Funcion iniciar lista

    DEBUG_PRINT(
        // tipo de informacion de debug
        DEBUG_LEVEL_INFO,

        // tipo de retorno y nombre funcion:
        INIT_TYPE_FUNC_DBG(Nodes *, InitList) 

        // final de la funcion:
        END_TYPE_FUNC_DBG);


    Nodes *Nodo; //= (Nodes *)malloc(sizeof(Nodes)); // Reservamos la memoria para el nodo
    debug_malloc(Nodes, Nodo, sizeof(Nodes));

    Nodo -> dato = 0; // Ponemos valor 0 al primer nodo
    Nodo -> NextNode = NULL; // Declaramos el siguiente como NULL para mas tarde asignarle valor
    Nodo -> LastNode = NULL; // Declaramos el anterior como NULL para mas tarde asignarle valor
    
    return Nodo; // Retornamos el nodo

}

Nodes *NextNode (Nodes *Nodo, uint8_t dato) {  // Funcion crear el siguiente Nodo
    // Recibimos el Nodo anterior y el dato

    DEBUG_PRINT(
        // tipo de informacion de debug
        DEBUG_LEVEL_INFO,

        // tipo de retorno y nombre funcion:
        INIT_TYPE_FUNC_DBG(Nodes *, NextNode) 
        
            // tipo de argumento, nombre del argumento y formato:
            TYPE_DATA_DBG(Nodes *, "Nodo = %p")
            TYPE_DATA_DBG(uint8_t, "dato = %hhu")

        // final de la funcion:
        END_TYPE_FUNC_DBG,

        // valores que usar para formatear
        Nodo, dato);


    Nodo -> NextNode = InitList(); // Guardamos el siguiente nodo
    Nodo -> NextNode -> dato = dato; // Le asignamos valor
    Nodo -> NextNode -> LastNode = Nodo; // Guardamos el nodo actual en el anterior nodo


    return Nodo -> NextNode; // Retornamos el nodo
    
}

void Print (Nodes* List) {  // Funcion imprimir lista

    DEBUG_PRINT(
        // tipo de informacion de debug
        DEBUG_LEVEL_INFO,

        // tipo de retorno y nombre funcion:
        INIT_TYPE_FUNC_DBG(void, Print) 
        
            // tipo de argumento, nombre del argumento y formato:
            TYPE_DATA_DBG(Nodes *, "List = %p")

        // final de la funcion:
        END_TYPE_FUNC_DBG,
        List);

    for (Nodes *i = List; i != NULL; i = i ->NextNode ){  // Recorremos la lista hasta el ultimo nodo que sera NULL 
        printf(
            "%p <----- %p = %hhu ----> %p\n", 
            i->LastNode,
            i, i->dato,
            i->NextNode
        );  // Imprimimos el ptr y el numero que le hemos asignado
        /*
            %P <----- %P = data ----> %p
            "%p <----- %p = %hhu ----> %p"
         */
    }


}

Nodes *Free (Nodes *List) {  // Funcion liberar memoria

    DEBUG_PRINT(
        // tipo de informacion de debug
        DEBUG_LEVEL_INFO,

        // tipo de retorno y nombre funcion:
        INIT_TYPE_FUNC_DBG(Nodes *, Free) 
        
            // tipo de argumento, nombre del argumento y formato:
            TYPE_DATA_DBG(Nodes *, "List = %p")

        // final de la funcion:
        END_TYPE_FUNC_DBG,
        List);

    uint8_t Contador = 0; 

    for (Nodes *NodoAnterior = List, *i = NodoAnterior; 
         i != NULL;
         Contador++, i = i -> NextNode){
            if (Contador == 0) continue;
            else {
                DEBUG_PRINT(DEBUG_LEVEL_INFO, "Memoria liberada para el nodo %p\n", NodoAnterior);
                free(NodoAnterior);
                NodoAnterior = i;
            }
        /* Mediante un bucle recorremos la lista mientras
            que guardamos el nodo anterior en una variable,
            lo compara con "NULL", es decir con el ultimo
            y si es diferente libera memoria del nodo pasado, y sigue
            incrementado sumando 1 a la variable contador.*/


    }

    return NULL;

}

void Delete (Nodes *Nodo1) {

    DEBUG_PRINT(
        // tipo de informacion de debug
        DEBUG_LEVEL_INFO,

        // tipo de retorno y nombre funcion:
        INIT_TYPE_FUNC_DBG(void, Delete) 
        
            // tipo de argumento, nombre del argumento y formato:
            TYPE_DATA_DBG(Nodes *, "Nodo1 = %p")

        // final de la funcion:
        END_TYPE_FUNC_DBG,
        Nodo1);

    Nodes *Nodo0 = Nodo1 -> LastNode ; // Guardamos el nodo 0 en su variable
    Nodes *Nodo2 = Nodo1 -> NextNode ; // Guardamos el nodo 2 en su variable

    Nodo2 -> LastNode = Nodo0; // Nodo 0 apunta a nodo 2
    Nodo0 -> NextNode = Nodo2; //Nodo 2 apunta a nodo 0

    free(Nodo1); // Liberamos memoria borrando el nodo 1

    /*
        Para que funcione esto, tenemos que guardar los nodos,
        que quereamos que se enlacen en variables y cuando,
        lo tengamos guardado los podremos enlazar, 
        una vez que este echo podremos liberar el nodo necesario.
    */

}


int main () {

    Nodes *List = InitList(); // Iniciamos lista

    Nodes *Node1 = NextNode(List, 1); // Creamos siguiente node con valor 2
    Nodes *Node2 = NextNode(Node1, 2);
    Nodes *Node3 = NextNode(Node2, 3);
    Nodes *Node4 = NextNode(Node3, 4);

    Delete(Node1);

    Print(List); // Imprimimos lista
    
    Free(List);  // Liberamos lista

    return 0;
}
#endif
```

``code.h``:
```c
#ifndef __CODE_H__
#define __CODE_H__

#include <stdio.h>
#include <stdint.h>
#include <stdlib.h>
#include "DebugLibC\debug_c.h"

typedef struct Nodes { /* Estructura la cual usaremos para crear el tipo 
                        de dato "Nodes" y crear los nodos y los datos*/

    uint8_t dato;  // Variable sin valor que usaremos para guardar los datos de los nodos
    struct Nodes * NextNode; // Variable puntero hacia siguiente nodo
    struct Nodes * LastNode; // Variable puntero hacia anterior nodo
    
} Nodes ;

Nodes *InitList ();

Nodes *NextNode (Nodes *Nodo, uint8_t dato);

void Print (Nodes* List);

Nodes *Free (Nodes *List);

#include "code.c"

#endif 
```
