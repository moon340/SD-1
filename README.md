#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <conio.h>  // Include conio.h for getch()

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

void login();
void options();

int main()
{
    login();

}

void login()
{
    printf("************************************\n");
    printf("*         Login - NexSuperMart            *\n");
    printf("************************************\n");
    char username[15], password[10];
    int i = 0;

    printf("Enter username: ");
    scanf("%s", username);

    printf("\nEnter password: ");
    while (1)
    {
        char ch = getch();  // Use getch() to capture characters without echoing
        if (ch == '\r')     // Check if Enter is pressed
        {
            password[i] = '\0';  // Null-terminate the password string
            break;
        }
        else if (ch == 8 && i > 0)  // Check if Backspace is pressed
        {
            printf("\b \b");  // Move the cursor back and erase the character
            i--;
        }
        else
        {
            password[i] = ch;  // Store the character in the password
            printf("*");      // Print a '*' to the console
            i++;
        }
    }

    while (1)
    {
        if ((strcmp(USERNAME, username) == 0) && (strcmp(PASSWORD, password) == 0))
        {
            printf("\033[0;32m");
            printf("\nLogged in successfully!\n");
            printf("\033[0m");
            system("cls");
            options();
            break;
        }
        else
        {
            system("cls");
            printf("\033[1;31m");
            printf("\nWrong Credential, Please try again!\n");
            printf("\033[0m");
            login();
            break;
        }
    }
}

void options()
{
    printf("**********************************\n");
    printf("*            NexSuperMart        *\n");
    printf("**********************************\n");

    printf("Options Coming Soon!\n");

};
