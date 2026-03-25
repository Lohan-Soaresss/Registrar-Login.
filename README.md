#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <locale.h>
int main()
{
    setlocale(LC_ALL,"portuguese");
    int opcao;
    char nome[100], senha[100];
    char bv[] = "Bem-vindo ";
    char final[200];
    do{
        printf(">MENU<\n1.Fazer Login\n0.Sair\nESCOLHA: ");
        scanf(" %d",&opcao);
        setbuf(stdin, NULL);
        switch(opcao){
            case 1:
                printf("Digite seu nome de usuário: ");
                fgets(nome, 100, stdin);
                nome[strcspn(nome, "\n")] = 0;

                do{

                printf("Digite sua senha: ");
                fgets(senha, 100, stdin);
                senha[strcspn(senha, "\n")] = 0;
                if(strcmp(nome, senha)==0){
                    printf("\nSenha não pode ser igual nome de usuário\n");
                }
                if(strlen(senha)<8){
                    printf("\nA senha precisa ter no mínimo 8 caracteres\n");
                }


                }while(strcmp(nome, senha)==0 || strlen(senha)<8);



            break;
            default:
                printf("Saindo...");
                return 0;
        }
        opcao = 0;
    }while(opcao!=0);
          printf("\n\n--LOGIN EFETUADO COM SUCESSO--\n\n");
          strcpy(final,bv);
          strcat(final,nome);
          printf("%s\n", final);

    return 0;
}# Registrar-Login.
Código básico para efetuar Login, com nome de usuário e senha.
