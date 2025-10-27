# Algoritmos de búsqueda en C (ANSI)

Los **algoritmos de búsqueda** son técnicas para encontrar un elemento específico dentro de una estructura de datos, como un arreglo. En C, los más usados son:

- **Búsqueda lineal/ secuencial**
- **Búsqueda binaria**
- (Extra: hay más como búsqueda hash, pero los dos anteriores son la base en arreglos)

Vamos a ver qué son, para qué sirven y cómo se implementan en C.

***

## 1. Búsqueda lineal

### ¿Qué es?

Es el método más simple: recorre el arreglo **de principio a fin** comparando cada elemento con el valor buscado.

### ¿Para qué sirve?

Sirve para buscar en **arreglos no ordenados** o pequeños. No necesita que los datos estén en orden.

### Ejemplo en la vida diaria

**Buscar un libro en una pila desordenada**: vas revisando uno a uno hasta encontrar el libro que quieres.

### Ejemplo de código en C comentado

```c
#include <stdio.h>

// Función de búsqueda lineal
printf("-**Ejemplo básico de búsqueda lineal**-");
int busquedaLineal(int arr[], int n, int clave) {
    for(int i = 0; i < n; i++) {            // Recorre desde el primer hasta el último elemento
        if(arr[i] == clave) {               // Si el elemento es igual al buscado
            return i;                       // Retorna la posición donde fue encontrado
        }
    }
    return -1;                             // Si no lo encuentra, retorna -1
}

int main() {
    int datos[] = {15, 22, 9, 31, 42};      // Arreglo de datos (desordenado)
    int tamano = 5;
    int buscado = 31;                       // Valor a buscar
    int pos = busquedaLineal(datos, tamano, buscado); // Llamada a la función

    if(pos != -1)
        printf("Elemento %d encontrado en la posición %d\n", buscado, pos);
    else
        printf("Elemento %d no encontrado\n", buscado);
    return 0;
}
```

**¿Listo para intentar escribir o modificar este código tú mismo? ¿Qué cambiarías si la lista tuviera el doble de elementos?**

---
## 2. Búsqueda binaria

### ¿Qué es?

Es un método eficiente para **arreglos ordenados**. Repite el proceso de dividir el arreglo en dos, descartando la mitad donde NO puede estar el dato, hasta encontrarlo.

### ¿Para qué sirve?

Sirve para buscar rápidamente en grandes cantidades de datos **ordenados** (como listas de clientes por ID).

### Ejemplo en la vida diaria

**Buscar una palabra en un diccionario ordenado**: abres el libro por la mitad, según la letra comparas y descarta la mitad incorrecta, repitiendo hasta hallarla.

### Ejemplo de código en C comentado

```c
#include <stdio.h>

// Función de búsqueda binaria
printf("-**Ejemplo básico de búsqueda binaria**-");
int busquedaBinaria(int arr[], int n, int clave) {
    int bajo = 0;              // Límite inferior del arreglo
    int alto = n - 1;          // Límite superior
    while (bajo <= alto) {
        int central = (bajo + alto) / 2;    // Calcula el centro
        if (arr[central] == clave)          // ¿Está justo en el centro?
            return central;                 // Retorna la posición encontrada
        else if (clave < arr[central])      // ¿El buscado es menor que el elemento central?
            alto = central - 1;             // Busca en la mitad inferior
        else
            bajo = central + 1;             // Busca en la mitad superior
    }
    return -1;                             // No se encontró
}

int main() {
    int datos[] = {9, 15, 22, 31, 42};      // Arreglo de datos ordenado
    int tamano = 5;
    int buscado = 31;                       // Valor a buscar
    int pos = busquedaBinaria(datos, tamano, buscado); // Llamada

    if(pos != -1)
        printf("Elemento %d encontrado en la posición %d\n", buscado, pos);
    else
        printf("Elemento %d no encontrado\n", buscado);
    return 0;
}
```

**¿Puedes pensar otra rutina donde la búsqueda binaria sería más rápida que la lineal?**

---
## Resumen activo

- **Lineal:** útil en listas no ordenadas o cortas.
- **Binaria:** mucho más rápida en listas ordenadas.