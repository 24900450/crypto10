# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```c
#include <stdio.h>

int main()
{
    int p, g, a, b;
    int A = 1, B = 1, keyA = 1, keyB = 1;
    int i;

    printf("Enter prime number (p): ");
    scanf("%d", &p);

    printf("Enter primitive root (g): ");
    scanf("%d", &g);

    printf("Enter private key of A: ");
    scanf("%d", &a);

    printf("Enter private key of B: ");
    scanf("%d", &b);

    // Calculate A = g^a mod p
    for(i = 0; i < a; i++)
    {
        A = (A * g) % p;
    }

    // Calculate B = g^b mod p
    for(i = 0; i < b; i++)
    {
        B = (B * g) % p;
    }

    printf("Public value from A: %d\n", A);
    printf("Public value from B: %d\n", B);

    // Shared key for A
    for(i = 0; i < a; i++)
    {
        keyA = (keyA * B) % p;
    }
    // Shared key for B
    for(i = 0; i < b; i++)
    {
        keyB = (keyB * A) % p;
    }

    printf("Secret key computed by A: %d\n", keyA);
    printf("Secret key computed by B: %d\n", keyB);

    return 0;
}
```


## Output:
<img width="616" height="429" alt="image" src="https://github.com/user-attachments/assets/2dae3442-2775-4fd9-a2b6-4b5592bc61ae" /><br>
## Result:
  The program is executed successfully

