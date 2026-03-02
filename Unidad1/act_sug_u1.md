# Actividad Práctica Sugerida
***

## 1. Algoritmo, programa y programación

Objetivo: ver la traducción de un algoritmo “leer dos números y sumarlos” a C.

```c
/* Algoritmo: leer dos numeros, sumarlos y mostrar el resultado */
#include <stdio.h>

int main(void) {
    int a, b, suma;

    printf("Ingresa el primer numero: ");
    scanf("%d", &a);

    printf("Ingresa el segundo numero: ");
    scanf("%d", &b);

    suma = a + b;

    printf("La suma de %d y %d es %d\n", a, b, suma);

    return 0;
}
```

***

## 2. Datos, variables y constantes

Objetivo: declarar distintos tipos y una constante, hacer una operación simple. 

```c
/* Uso de variables y una constante */
#include <stdio.h>

#define IVA 0.16   /* constante simbólica */

int main(void) {
    float precio_base;
    float precio_final;

    printf("Ingresa el precio base del producto: ");
    scanf("%f", &precio_base);

    precio_final = precio_base * (1 + IVA);

    printf("Precio base: %.2f\n", precio_base);
    printf("IVA aplicado: %.2f\n", IVA);
    printf("Precio final: %.2f\n", precio_final);

    return 0;
}
```

***

## 3. Estructuras de control

Objetivo: usar secuencia, selección (`if`) y repetición (`for`). 

```c
/* Estructuras de control: if y for */
#include <stdio.h>

int main(void) {
    int i, n;

    printf("Ingresa un numero entero positivo: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("El numero no es positivo.\n");
    } else {
        printf("Contando desde 1 hasta %d:\n", n);
        for (i = 1; i <= n; i++) {
            printf("%d ", i);
        }
        printf("\n");
    }

    return 0;
}
```

***

## 4. Funciones y modularidad

Objetivo: separar una tarea en una función que recibe datos y regresa resultado. 

```c
/* Funciones: calculo del maximo de dos numeros */
#include <stdio.h>

int maximo(int x, int y) {
    int max;
    if (x > y) {
        max = x;
    } else {
        max = y;
    }
    return max;
}

int main(void) {
    int a, b, m;

    printf("Ingresa el primer numero: ");
    scanf("%d", &a);

    printf("Ingresa el segundo numero: ");
    scanf("%d", &b);

    m = maximo(a, b);

    printf("El mayor entre %d y %d es %d\n", a, b, m);

    return 0;
}
```

***

## 5. Lógica de algoritmos

Objetivo: practicar condiciones compuestas (par / impar y positivo / negativo). 

```c
/* Logica de algoritmos: clasificacion de un numero */
#include <stdio.h>

int main(void) {
    int n;

    printf("Ingresa un numero entero: ");
    scanf("%d", &n);

    if (n > 0) {
        printf("El numero es positivo");
    } else if (n < 0) {
        printf("El numero es negativo");
    } else {
        printf("El numero es cero");
    }

    if (n != 0) {
        if (n % 2 == 0) {
            printf(" y par.\n");
        } else {
            printf(" e impar.\n");
        }
    } else {
        printf(".\n");
    }

    return 0;
}
```

***

## 6. Lenguajes de programación y paradigmas (en C)

Objetivo: mostrar un mini “menú” que ilustre que C es imperativo/estructurado y mencionar otros paradigmas en la salida.

```c
/* Lenguajes y paradigmas: ejemplo de menu en C (imperativo) */
#include <stdio.h>

int main(void) {
    int opcion;

    printf("Paradigmas de programacion\n");
    printf("1) Imperativo / Estructurado (ejemplo: C)\n");
    printf("2) Orientado a objetos (ejemplo: Java, C++)\n");
    printf("3) Funcional (ejemplo: Haskell)\n");
    printf("4) Logico (ejemplo: Prolog)\n");

    printf("Elige una opcion (1-4): ");
    scanf("%d", &opcion);

    if (opcion == 1) {
        printf("Has elegido el paradigma imperativo / estructurado.\n");
    } else if (opcion == 2) {
        printf("Has elegido el paradigma orientado a objetos.\n");
    } else if (opcion == 3) {
        printf("Has elegido el paradigma funcional.\n");
    } else if (opcion == 4) {
        printf("Has elegido el paradigma logico.\n");
    } else {
        printf("Opcion no valida.\n");
    }

    return 0;
}
```

***

## 7. Ejemplo “mínimo” de programa completo

Objetivo: ver la estructura estándar de un programa en C, `main`, `printf`, `return`. 

```c
/* Estructura minima de un programa en C */
#include <stdio.h>

int main(void) {
    printf("Hola, este es mi primer programa en C.\n");
    return 0;
}
```
