# EX.-NO-1-B-IMPLEMENTATION-OF-PLAYFAIR-CIPHER

## AIM:
  To write a C program to implement the Playfair Substitution technique.
  
## ALGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the keyword from the user.

STEP-3: Arrange the keyword without duplicates in a 5*5 matrix in the row order and fill the remaining cells with missed out letters in alphabetical order. Note that ‘i’ and ‘j’ takes the same cell.

STEP-4: Group the plain text in pairs and match the corresponding corner letters by forming a rectangular grid.

STEP-5: Display the obtained cipher text.

## PROGRAM:
#include<stdio.h>
#include<string.h>

int main() {
    unsigned int a[3][3] = {{6, 24, 1}, {13, 16, 10}, {20, 17, 15}};
    unsigned int b[3][3] = {{8, 5, 10}, {21, 8, 21}, {21, 12, 8}};
    int i, j, k, t;
    unsigned int c[3], d[3];
    char msg[4];

    printf("Enter plain text (3 letters): ");
    scanf("%3s", msg);  // Limiting input to 3 characters

    for (i = 0; i < 3; i++) {
        c[i] = msg[i] - 65;  // Converting letters to numbers (A=0, B=1, ..., Z=25)
    }

    // Encryption
    for (i = 0; i < 3; i++) {
        t = 0;
        for (j = 0; j < 3; j++) {
            t += a[i][j] * c[j];
        }
        d[i] = t % 26;
    }

    printf("\nEncrypted Cipher Text: ");
    for (i = 0; i < 3; i++) {
        printf("%c", d[i] + 65);  // Converting numbers back to letters
    }

    // Decryption
    for (i = 0; i < 3; i++) {
        t = 0;
        for (j = 0; j < 3; j++) {
            t += b[i][j] * d[j];
        }
        c[i] = t % 26;
    }

    printf("\nDecrypted Cipher Text: ");
    for (i = 0; i < 3; i++) {
        printf("%c", c[i] + 65);  // Converting numbers back to letters
    }

    printf("\n");

return 0;
}

## OUTPUT:
![Screenshot 2024-09-11 094351](https://github.com/user-attachments/assets/e7c4b989-ab4e-4fcc-96a8-50db62705864)


## RESULT:
  Thus the Playfair cipher substitution technique had been implemented successfully.
