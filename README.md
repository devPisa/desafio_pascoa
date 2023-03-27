#include <stdio.h>
#include <math.h>

int main() {
    int Y;
    int G, C, X, Z, E, N, D;
    char escolha;

    do{

    printf("Quando sera a Pascoa de ");
    scanf("%d", &Y);

    if (Y<=1582){
        printf("Insira uma data entre 1582 e 4999.\n");
    }
    else{
    G = (Y%19) + 1;
    C = (Y / 100) + 1;
    X = (3 * C / 4) - 12;
    Z = (8 * C + 5) / 25 - 5;
    E = fmod(11 * G + 20 + Z - X, 30);
    if ((E == 25 && G > 11) || E == 24) {
        E += 1;
    }
    N = 44 - E;
    if (N < 21) {
        N += 30;
    }
    D = (5 * Y) / 4 - (X + 10);
    N = (N + 7) - fmod(D + N, 7);

    if (N > 31) {
        printf("Pascoa: %d de abril de %d.\n", (int) (N - 31),Y);
     }
     else
        {
        printf("Pascoa: %d de marco de %d.\n", (int) N,Y);
        }
     printf("Deseja verificar outra data? (S) ou (N)\n");
     scanf("%s", &escolha);
    }
    }
        while(escolha == 'S' || escolha =='s' || 	escolha == 'Sim' || escolha == 'sim');
}
