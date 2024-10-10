# 19CS415-AES-Encryption-and-decryption
## AIM:
To Encrypt and Decrypt a given message using Advanced Encryption Standard (AES) Algorithm.

## ALGORITHM:
1.  AES is based on a design principle known as a substitution–permutation.
2.  AES does not use a Feistel network like DES, it uses variant of Rijndael.
3.  It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
4.  AES operates on a 4 × 4 column-major order array of bytes, termed the state
   
## PROGRAM:
```c
#include <stdio.h>
#include <string.h>

void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext)
{
    int i;
    for (i = 0; i < strlen(plaintext); i++) 
    {
        ciphertext[i] = plaintext[i] ^ key[i % strlen(key)]; 
    }
    ciphertext[i] = '\0'; 
}

void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText)
{
    int i;
    for (i = 0; i < strlen(ciphertext); i++) 
    {
        decryptedText[i] = ciphertext[i] ^ key[i % strlen(key)]; 
    }
    decryptedText[i] = '\0'; 
}

void printASCII(char *ciphertext) 
{
    printf("Encrypted Message (ASCII values): ");
    for (int i = 0; i < strlen(ciphertext); i++) 
    {
        printf("%d ", (unsigned char)ciphertext[i]); 
    }
    printf("\n");
}

int main() 
{
    char plaintext[100], key[100], ciphertext[100], decryptedText[100];

    printf("Enter the plaintext: ");
    scanf("%s", plaintext);

    printf("Enter the key: ");
    scanf("%s", key);

    simpleAESEncrypt(plaintext, key, ciphertext);
    printASCII(ciphertext);  

    simpleAESDecrypt(ciphertext, key, decryptedText);
    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}

```
## OUTPUT:
![Screenshot 2024-10-10 094226](https://github.com/user-attachments/assets/8aca8ff8-40f3-449f-8fb0-e156e5330581)

## RESULT:
The program for AES algorithm is executed successfully.
