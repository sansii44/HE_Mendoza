#include <stdio.h>

int main() {
    float balance = 500.00;
    int choice;
    float amount;

    do {
        printf("SANSI BANK\n");
        printf("Please Select your Transaction\n");
        printf("[1] Balance Inquiry\n");
        printf("[2] Deposit\n");
        printf("[3] Withdraw\n");
        printf("[4] Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);  

        switch (choice) {
            case 1:
                printf("\nYour current balance: P%.2f\n", balance); 
            break;

            case 2:
                printf("Enter amount to deposit: ");
                scanf("%f", &amount); 
                if (amount <= 0) {
                    printf("Invalid deposit amount!\n");
                } else {
                    balance += amount;
                    printf("\nP%.2f deposited successfully!\n", amount); 
                }
                break;

            case 3:
                printf("Enter amount to withdraw: ");
                scanf("%f", &amount); 

                if (amount <= 0) {
                    printf("Invalid amount!\n");
                } else if (amount > balance - 100) {
                    printf("Withdrawal denied! You must maintain at least P100.00 in your account.\n");
                } else {
                    balance -= amount;
                    printf("Withdrawn successfully!\n");
                    printf("Remaining balance: P%.2f\n", balance);
                }
                break;

            case 4:
                printf("Exiting...\n");
                break;

            default:
                printf("Invalid choice. Please try again.\n");  
                break;
        }

        if (choice != 4) {
            printf("\n"); 
        }

    } while (choice != 4);

    printf("\nThank you for using SANSI BANK. Goodbye!\n"); 

    return 0;
}
