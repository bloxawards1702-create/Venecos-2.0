#include <stdio.h>

// Saludo inicial
void saludarUsuario() {
    printf("=============================================\n");
    printf("     ¡Bienvenido al Simulador Venezolano!    🇻🇪\n");
    printf("=============================================\n\n");
}

// Convertir bolívares a dólares
float bolivaresADolares(float sueldo, float tasa) {
    return sueldo / tasa;
}

// Recomendación de compra
void recomendacionCompra(float dolares) {
    if (dolares > 100) {
        printf("Recomendación: Nivel BODEGÓN 😎\n");
        printf("Puedes comprar Nutella, jamón serrano, una botella de agua importada de Islandia y una que otras curditas.\n");
    } else if (dolares >= 50 && dolares <= 100) {
        printf("Recomendación: Mercado y empanadita 🥟\n");
        printf("No es lujoso, pero se come pues peor es nada diria mi abuelo.\n");
    } else {
        printf("Recomendación: Arroz con lentejas 😭\n");
        printf("Coño chamo... fuerza mental y pa` lante.\n");
    }
}

// Transporte (si tiene carro o no)
void verificarTransporte() {
    char opcion;
    printf("\n¿Tienes carro? (S/N): ");
    scanf(" %c", &opcion);

    if (opcion == 'S' || opcion == 's') {
        printf("Consejo: Intenta echar gasolina... Pero trata de meterte o coliado o en la menos larga :v 🪑⛽\n");
    } else {
        printf("Consejo: Toca en buseta o chiripero papa... Claro, si pasa jeje... 🚍\n");
    }
}

int main() {
    char nombre[30];
    float sueldo, dolares;
    float tasa;
    int opcionTasa;
    int repetir = 1;

    while(repetir == 1) {

        saludarUsuario();

        printf("Ingresa tu nombre: ");
        scanf("%s", nombre);

        printf("Ingresa tu sueldo mensual (Bs): ");
        scanf("%f", &sueldo);

        printf("\nSelecciona la tasa del dólar:\n");
        printf("1. la del banco ineficiente (200 Bs)\n");
        printf("2. la del mercado negro (300 Bs)\n");
        printf("3. Tasa binance pero que nadie tiene binance :v (350 Bs)\n");
        printf("4. como lo vende la vieja de la esquina (400 Bs 🤯)\n");
        printf("Elige una opción (1-4): ");
        scanf("%d", &opcionTasa);

        switch(opcionTasa) {
            case 1: tasa = 200.0; break;
            case 2: tasa = 220.0; break;
            case 3: tasa = 210.0; break;
            case 4: tasa = 300.0; break;
            default:
                printf("Opción inválida, se usará el banco ineficiente por defecto (BCV) hola encontraste un easter egg, soy yo rompiendo la cuarta pared, ya se que estas testeando esto :v.\n");
                tasa = 200.0;
                break;
        }

        dolares = bolivaresADolares(sueldo, tasa);

        printf("\n%s, eso equivale a %.2f dólares 💵\n\n", nombre, dolares);

        recomendacionCompra(dolares);

        verificarTransporte();

        printf("\n¿Quieres volver a simular? (1 = Sí / 0 = No): ");
        scanf("%d", &repetir);

        printf("\n---------------------------------------------\n\n");
    }

    printf("Gracias por usar mi Simulador Venezolano ❤️\n");
    printf("Nos vemos cuando suba el dólar otra vez... o sea, mañana (Incluso hoy mismo).\n");

    return 0;
}
