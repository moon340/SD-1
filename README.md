#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#define USERNAME "admin"
#define PASSWORD "1234"
#define MAX 20

typedef struct items
{
    char product_code[MAX];
    char product_name[MAX];
    int rate;
    int quantity;
    float weight;
    char description[30];

} ITEM;

ITEM item;

int main()
{
    login();
    system("cls");
    return 0;
}

void login()
{
    printf("************************************\n");
    printf("*         Login - Agora            *\n");
    printf("************************************\n");
    char username[15], password[10];
    printf("Enter username: ");
    scanf("%s", username);
    printf("\nEnter password: ");
    scanf("%s", password);
    while (1)
    {
        if ((strcmp(USERNAME, username)) == 0 && (strcmp(PASSWORD, password)) == 0)
        {
            printf("\033[0;32m");
            printf("\nLogged in successfully!\n");
            printf("\033[0m");
            system("cls");
            options();
        }
        else
        {
            system("cls");
            printf("\033[1;31m");
            printf("\nWrong Credential,Please try again!\n");
            printf("\033[0m");
            login();
            break;
        }
    }
}

void options()
{
    printf("**********************************\n");
    printf("*            Agora               *\n");
    printf("**********************************\n");

    printf("Options Coming Soon!");
    return 0;

}
