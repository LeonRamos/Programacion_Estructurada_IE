# Estructuras Selectivas si, si entonces sino, si multiple. 

Las estructuras lógicas selectivas se encuentran en la solución algorítmica de casi todo tipo de problemas. Las utilizamos cuando en el desarrollo de la solución de un problema debemos tomar una decisión, para establecer un proceso o señalar un camino alternativo a seguir.

Esta toma de decisión (expresada en el diagrama de flujo con un rombo) se basa en la evaluación de una o más condiciones que nos señalarán como alternativa o consecuencia, la rama a seguir.

Hay situaciones en las que la toma de decisiones se realiza en cascada. Es decir se toma una decisión, se marca la rama correspondiente a seguir, se vuelve a tomar otra decisión y así sucesivamente. Por lo que para alcanzar la solución de un problema o subproblema debemos aplicar prácticamente un árbol de decisión.

Las **estructuras selectivas** son formas de controlar el flujo de ejecución de un algoritmo al tomar decisiones, permitiendo elegir entre diferentes caminos según una o varias condiciones. Se representan en diagramas de flujo mediante un rombo y existen de tipo "si", "si entonces sino" (doble) y "si múltiple" (varias alternativas).

## Tipos de estructuras selectivas

- **Simple (si):** Ejecuta una acción si la condición es verdadera; si es falsa, no ocurre nada.
- **Doble (si entonces sino):** Si la condición es verdadera, ejecuta una acción; si es falsa, ejecuta otra.
- **Múltiple (si múltiple):** Permite seleccionar entre varias acciones según el valor de una expresión o variable, como con `switch` en C o `if-elif-else` en Python.

Estas estructuras permiten decisiones en cascada, formando árboles de decisión para resolver problemas cada vez que se presenta una disyuntiva.

***

### Ejemplo

**Problema:** Dado un número, determinar si es positivo, negativo o cero (estructura selectiva múltiple).

***

#### DFD (Diagrama de Flujo de Datos)

1. Inicio
2. Leer número
3. ¿Número > 0?
    - Sí → Imprimir "Positivo"
    - No → ¿Número < 0?
        - Sí → Imprimir "Negativo"
        - No → Imprimir "Cero"
4. Fin

Este flujo se dibuja con un rombo (decisión) y ramas para cada alternativa.

***

#### Python

```python
num = int(input("Ingrese un número: "))
if num > 0:
    print("Positivo")
elif num < 0:
    print("Negativo")
else:
    print("Cero")
```


***

#### C

```c
#include <stdio.h>
int main() {
    int num;
    printf("Ingrese un número: ");
    scanf("%d", &num);
    if (num > 0) {
        printf("Positivo\n");
    } else if (num < 0) {
        printf("Negativo\n");
    } else {
        printf("Cero\n");
    }
    return 0;
}
```


***