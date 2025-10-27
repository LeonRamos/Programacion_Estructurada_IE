# ahora para los algoritmos de ordenamiento en c

Los algoritmos de ordenamiento en C son técnicas para organizar elementos en un arreglo según un criterio, como el orden numérico ascendente. Los que se enseñan comúnmente en C ANSI incluyen:

***

## 1. Ordenamiento por burbuja (Bubble Sort)

### Qué es y para qué sirve

Es un algoritmo simple que compara elementos adyacentes y los intercambia si están en el orden incorrecto. Se repite hasta que el arreglo esté ordenado. Es útil para listas pequeñas o educativas.

### Ejemplo de vida diaria

Ordenar una fila de personas por altura, intercambiando posiciones de dos personas cada vez que la persona de atrás sea más baja que la de adelante.

### Código en C comentado

```c
#include <stdio.h>

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {               // Recorrer el arreglo varias veces
        for (int j = 0; j < n-i-1; j++) {         // Comparar pares adyacentes
            if (arr[j] > arr[j+1]) {               // Si el anterior es mayor que el siguiente
                int temp = arr[j];                  // Guardar temporalmente el valor
                arr[j] = arr[j+1];                  // Intercambiar los elementos
                arr[j+1] = temp;
            }
        }
    }
}

int main() {
    int datos[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(datos)/sizeof(datos[^0]);

    bubbleSort(datos, n);

    printf("Arreglo ordenado: ");
    for (int i=0; i < n; i++)
        printf("%d ", datos[i]);
    printf("\n");
    return 0;
}
```


***

## 2. Ordenamiento por inserción (Insertion Sort)

### Qué es y para qué sirve

Construye el arreglo ordenado tomando un elemento a la vez e insertándolo en la posición correcta. Bueno para listas pequeñas o casi ordenadas.

### Ejemplo de vida diaria

Colocar cartas en tu mano para que siempre estén en orden, tomando una carta de la mesa y poniéndola en la posición correcta.

### Código en C comentado

```c
#include <stdio.h>

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {              // Inicia desde el segundo elemento
        int key = arr[i];                      // Elemento actual a insertar
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {      // Mover elementos mayores a la derecha
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;                      // Insertar la clave en su lugar correcto
    }
}

int main() {
    int datos[] = {12, 11, 13, 5, 6};
    int n = sizeof(datos)/sizeof(datos[^0]);

    insertionSort(datos, n);

    printf("Arreglo ordenado: ");
    for (int i=0; i < n; i++)
        printf("%d ", datos[i]);
    printf("\n");
    return 0;
}
```


***

## 3. Ordenamiento rápido (Quicksort)

### Qué es y para qué sirve

Es un algoritmo eficiente que usa la técnica de divide y vencerás. Selecciona un pivote, divide el arreglo en partes menores y mayores que el pivote y ordena recursivamente. Es muy eficiente para listas grandes.

### Ejemplo de vida diaria

Organizar libros en una biblioteca seleccionando un libro como referencia (pivote) y colocando libros más pequeños a la izquierda y más grandes a la derecha, repitiendo el proceso en cada sección.

### Código en C comentado

```c
#include <stdio.h>

// Función para intercambiar dos elementos
void swap(int* a, int* b) {
    int t = *a;
    *a = *b;
    *b = t;
}

// Función que realiza la partición
int partition(int arr[], int low, int high) {
    int pivot = arr[low];         // Pivote como primer elemento
    int left = low + 1;
    int right = high;

    while (left <= right) {
        while (left <= right && arr[left] <= pivot)
            left++;                // Avanzar hasta encontrar elemento mayor que pivote
        while (left <= right && arr[right] > pivot)
            right--;               // Retroceder hasta encontrar elemento menor o igual
        if (left < right)
            swap(&arr[left], &arr[right]);  // Intercambiar elementos fuera de lugar
    }
    swap(&arr[low], &arr[right]);   // Colocar pivote en su posición correcta
    return right;
}

// Función QuickSort recursiva
void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int p = partition(arr, low, high);    // Particiona y obtiene posición pivote
        quickSort(arr, low, p - 1);            // Ordena la parte izquierda
        quickSort(arr, p + 1, high);           // Ordena la parte derecha
    }
}

int main() {
    int datos[] = {10, 7, 8, 9, 1, 5};
    int n = sizeof(datos)/sizeof(datos[^0]);

    quickSort(datos, 0, n - 1);

    printf("Arreglo ordenado: ");
    for (int i=0; i < n; i++)
        printf("%d ", datos[i]);
    printf("\n");
    return 0;
}
```


***

Para cada algoritmo, aquí van enunciados simples para un problema de la vida real a resolver mediante ordenamiento:

- Burbuja: Ordenar una lista corta de calificaciones escolares para asignar recompensas por orden de nota.
- Inserción: Organizar ingresos diarios en una pequeña tienda para facilitar el registro contable ordenado.
- Quicksort: Ordenar una base de datos grande de clientes por número de cliente para búsquedas rápidas.
