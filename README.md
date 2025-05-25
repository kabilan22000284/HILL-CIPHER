# HILL CIPHER
## EX. NO: 3 
## Name: KABILAN V
## Reg no: 212222100018

## AIM: 
IMPLEMENTATION OF HILL CIPHER

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

1.Convert each letter of the message to a number (A = 0, B = 1, ..., Z = 25) and divide the message into blocks of size n.

2.Select an invertible n × n matrix as the cipher key (modulo 26 for the English alphabet).

3.Multiply each block of n letters by the cipher key matrix (modulo 26) to get the encrypted numbers.

4.Convert the encrypted numbers back into letters using the reverse of step 1.

5.Multiply the encrypted blocks by the inverse of the cipher key matrix (modulo 26) to recover the original message.

6.Ensure the key matrix is invertible (mod 26) for decryption to be possible.

## PROGRAM 
```
#include <stdio.h> 
#include <string.h> 
int main() 
{
    unsigned int a[3][3] = {{6, 24, 1}, {13, 16, 10}, {20, 17, 15}};
    unsigned int b[3][3] = {{8, 5, 10}, {21, 8, 21}, {21, 12, 8}};
    int i, j, t = 0;
    unsigned int c[3], d[3];
    char msg[4]; 
    printf("Enter plain text (3 letters): ");
    scanf("%3s", msg); 
    if (strlen(msg) != 3) 
    {
        printf("Error: The plain text must be exactly 3 letters.\n"); 
        return 1;
        
    }
    
    for (i = 0; i < 3; i++) 
    {
        c[i] = msg[i] - 'A';
        printf("%d ", c[i]); 
        
    }
    for (i = 0; i < 3; i++) 
    {
        t = 0;
        for (j = 0; j < 3; j++) 
        { 
            t += a[i][j] * c[j];
            
        }
        d[i] = t % 26; 
        
    }
    printf("\nEncrypted Cipher Text: "); 
    for (i = 0; i < 3; i++) 
    {
        printf("%c", d[i] + 'A');
        
    }
    for (i = 0; i < 3; i++) 
    {
        t = 0;
        for (j = 0; j < 3; j++) 
        { 
            t += b[i][j] * d[j];
            
        }
        c[i] = t % 26; 
        
    }
    printf("\nDecrypted Cipher Text: "); 
    for (i = 0; i < 3; i++) 
    {
        printf("%c", c[i] + 'A');
        
    }
    getchar(); 
    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/175b9462-bf12-45ce-a0d8-bc50f7b4881e)



## RESULT
The program is executed successfully
