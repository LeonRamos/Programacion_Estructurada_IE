Fase 2: Implementación Manual
En C (Enfoque Estructurado)
C
#include <stdio.h>

int main() {
    int edad, horas;
    float total;

    printf("--- Sistema de Estacionamiento ---\n");
    printf("Ingrese su edad: ");
    scanf("%d", &edad);

    if (edad < 18) {
        printf("Acceso denegado. Debe ser mayor de edad para conducir.\n");
    } else {
        printf("¿Cuantas horas permanecio el vehiculo? ");
        scanf("%d", &horas);

        total = horas * 3.0;

        if (horas > 5) {
            total = total * 0.90; // Descuento del 10%
            printf("¡Se aplico un descuento por larga estancia!\n");
        }

        printf("El total a pagar es: $%.2f\n", total);
    }
    return 0;
}
En Python (Enfoque Secuencial Simple)
Python
print("--- Sistema de Estacionamiento ---")
edad = int(input("Ingrese su edad: "))

if edad < 18:
    print("Acceso denegado. Debe ser mayor de edad.")
else:
    horas = int(input("¿Cuántas horas permaneció el vehículo? "))
    total = horas * 3.0
    
    if horas > 5:
        total *= 0.90
        print("¡Se aplicó un descuento del 10%!")
        
    print(f"El total a pagar es: ${total:.2f}")
