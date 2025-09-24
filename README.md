# Ex-4 Rail-Fence-Program

## IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE
## NAME-SRILAKSHMI.B.H
## REG-212224100057

## AIM:

 To write a C program to implement the rail fence transposition technique.

## DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

## ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

## PROGRAM

```
#include <stdio.h>
#include <string.h>
int main()
{
int i, j, k, l;
char a[20], c[20], d[20];
printf("\n\t\tRAIL FENCE TECHNIQUE\n");
printf("\nEnter the input string: ");
fgets(a, sizeof(a), stdin);
l = strlen(a);
for (i = 0, j = 0; i < l; i++)
{
    if (i % 2 == 0)
    {
    c[j++] = a[i];
    }
}
for (i = 0; i < l; i++)
{
    if (i % 2 == 1)
    {
    c[j++] = a[i];
    }
}
c[j] = '\0'; 
printf("\nCipher text after applying rail fence: %s\n", c); 
if(l%2==0)
{
k = l / 2;
}
else
{
k = (l / 2) + 1;
}
for (i = 0, j = 0; i < k; i++)
{
d[j] = c[i]; j += 2;
}
for (i = k, j = 1; i < l; i++)
{
d[j] = c[i]; j += 2;
}
d[l] = '\0'; 
printf("\nText after decryption: %s\n", d);
return 0;
}
```
## OUTPUT

<img width="735" height="385" alt="Screenshot 2025-09-24 at 1 30 20 PM" src="https://github.com/user-attachments/assets/34a4f32a-aaaf-4202-ac4b-c40d7da98247" />


## RESULT

The program is executed successfully
