# Conceptos Fundamentales de la Programación

## 1.3 Conceptos fundamentales

Esta sección estudia los conceptos clave para construir algoritmos, diagramas de flujo y programas, comenzando por los tipos de datos, identificadores, constantes, variables y operaciones aritméticas. Son fundamentos para la programación estructurada.

### 1.3.1 Tipos de datos

Los datos procesados por una computadora pueden clasificarse en:
- **Simples**, los cuales ocupan una sola celda de memoria. Ejemplos: enteros, reales, caracteres, booleanos, enumerados, subrangos.
- **Estructurados**, que ocupan varias celdas de memoria y agrupan componentes. Ejemplos: arreglos, cadenas, registros, conjuntos.

**Ejemplos de datos simples**:
- Enteros: `128`, `1528`, `-714`, `8530`
- Reales: `7.5`, `128.0`, `-37.865`
- Caracteres: `'a'`, `'B'`, `'$'`, `'9'`
- Cadenas: `"Carlos Gómez"`, `"754-27-22"`
- Booleanos: `true`, `false`

### 1.3.2 Identificadores, constantes y variables

**Identificadores**

Un identificador es el nombre asignado a una celda de memoria, compuesto por letras, números y el guion bajo, iniciando siempre con una letra. Ejemplos: SUMA, AUX, NUM_1, X7.

**Constantes**

Son datos que no cambian durante la ejecución del programa, y pueden ser de tipo entero, real, carácter o cadena. Ejemplo: NUM, NREAL, RESU.

**Variables**

Son objetos cuya valor puede modificarse durante la ejecución del programa. Ejemplo: I, SUMA, SUEL. Los nombres deben ser representativos de la función que cumplen en el algoritmo. [attached_file:1]

### 1.3.3 Operaciones aritméticas

Para efectuar operaciones aritméticas se emplean los siguientes operadores:

| Operador Aritmético | Operación         | Ejemplo           | Resultado |
|:-------------------:|:----------------:|:-----------------:|:---------:|
| **                  | Potencia          | 4**3              | 64        |
| *                   | Multiplicación    | 8.25*7            | 57.75     |
| /                   | División          | 15/4              | 3.75      |
| +                   | Suma              | 125.78 + 62.50    | 188.28    |
| -                   | Resta             | 65.30 - 32.33     | 32.97     |
| mod                 | Módulo (residuo)  | 15 mod 2          | 1         |
| div                 | División entera   | 17 div 3          | 5         |

Al evaluar expresiones con varios operadores, se respeta la jerarquía de los mismos:
1. Paréntesis `()`
2. Potencia `**`
3. Multiplicación, división, módulo, división entera (`*`, `/`, `mod`, `div`)
4. Suma y resta (`+`, `-`)

| Operador           | Jerarquía | Operación                             |
|:------------------:|:---------:|:-------------------------------------:|
| **                 | (mayor)   | Potencia                              |
| */, mod, div       |           | Multiplicación, división, módulo, división entera |
| +, -               | (menor)   | Suma, resta                           |

Las reglas básicas:
- Las subexpresiones entre paréntesis se evalúan antes que el resto, respetando siempre la jerarquía.
- Si hay más de un nivel de paréntesis, se evalúan primero los del nivel más interno.

> Resolver los ejemplos 1.2 al 1.10 del libro de la clase metodología de la programción de Osvaldo Cairo. 
