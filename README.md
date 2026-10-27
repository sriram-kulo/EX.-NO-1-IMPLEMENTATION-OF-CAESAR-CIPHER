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
#include <string.h>

int main(void)
{
    char text[1000];
    int key;

    printf("Enter plain text: ");
    if (fgets(text, sizeof(text), stdin) == NULL) {
        fprintf(stderr, "Error reading plain text.\n");
        return 1;
    }

    text[strcspn(text, "\n")] = '\0';

    printf("Enter key: ");
    if (scanf("%d", &key) != 1) {
        fprintf(stderr, "Invalid key.\n");
        return 1;
    }

    int shift = key % 26;
    for (size_t i = 0; text[i] != '\0'; i++) {
        if (text[i] >= 'A' && text[i] <= 'Z') {
            text[i] = (char)('A' + (text[i] - 'A' + shift + 26) % 26);
        } else if (text[i] >= 'a' && text[i] <= 'z') {
            text[i] = (char)('a' + (text[i] - 'a' + shift + 26) % 26);
        }
    }

    printf("Cipher text: %s\n", text);
    return 0;
}
```
## OUTPUT:
<img width="248" height="88" alt="image" src="https://github.com/user-attachments/assets/e3217cb9-1449-45ce-bd10-d56cf7271bfb" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
