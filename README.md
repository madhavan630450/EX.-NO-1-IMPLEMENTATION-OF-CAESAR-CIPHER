# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

int main() {
    char text[100], encrypted[100], decrypted[100];
    int key, i;

    printf("Enter text: ");
    fgets(text, sizeof(text), stdin);

    text[strcspn(text, "\n")] = '\0';

    printf("Enter key: ");
    scanf("%d", &key);

    for(i = 0; text[i] != '\0'; i++) {
        char ch = text[i];

        if(isalpha(ch)) {
            char base = islower(ch) ? 'a' : 'A';
            encrypted[i] = (ch - base + key) % 26 + base;
        } else {
            encrypted[i] = ch;
        }
    }
    encrypted[i] = '\0';

    for(i = 0; encrypted[i] != '\0'; i++) {
        char ch = encrypted[i];

        if(isalpha(ch)) {
            char base = islower(ch) ? 'a' : 'A';
            decrypted[i] = (ch - base - key + 26) % 26 + base;
        } else {
            decrypted[i] = ch;
        }
    }
    decrypted[i] = '\0';

    printf("Encrypted: %s\n", encrypted);
    printf("Decrypted: %s\n", decrypted);

    return 0;
}
```

## OUTPUT:

<img width="1757" height="986" alt="Screenshot 2026-04-29 091645" src="https://github.com/user-attachments/assets/12abb8bd-a1ad-4a86-9704-4868d270441c" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
