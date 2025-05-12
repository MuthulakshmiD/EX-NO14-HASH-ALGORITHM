# EX-NO14-HASH-ALGORITHM
##### Muthulakshmi D - 212223040122
## AIM:
To implement HASH ALGORITHM

## ALGORITHM:

1. Hash Algorithm is used to convert input data (message) into a fixed-size string, typically a hash value, which uniquely represents the original data.

2. Initialization:
   - Choose a hash function \( H \) (e.g., SHA-256, MD5, etc.).
   - The message \( M \) to be hashed is input.

3. Message Preprocessing:
   - Break the message \( M \) into fixed-size blocks. If necessary, pad the message to make it compatible with the block size required by the hash function.
   - For example, in SHA-256, the message is padded to ensure that its length is a multiple of 512 bits.

4. Hash Calculation:
   - Process the message block by block, applying the hash function \( H \) iteratively to produce an intermediate hash value.
   - For SHA-256, each block is processed through a series of logical operations, bitwise manipulations, and modular additions.

5. Output:
   - After all blocks are processed, the final hash value (digest) is produced, which is a fixed-size output (e.g., 256-bit for SHA-256).
   - The resulting hash is unique to the input message, meaning even a small change in the message will result in a completely different hash.

6. Security: The strength of the hash algorithm lies in its collision resistance, ensuring that it is computationally infeasible to find two different messages that produce the same hash value.


## Program:
```
def encrypt(plaintext: str, shift: int) -> str:
    ciphertext = ""
    for ch in plaintext:
        if 'A' <= ch <= 'Z':
            ciphertext += chr((ord(ch) - ord('A') + shift) % 26 + ord('A'))
        elif 'a' <= ch <= 'z':
            ciphertext += chr((ord(ch) - ord('a') + shift) % 26 + ord('a'))
        else:
            ciphertext += ch
    return ciphertext

def decrypt(ciphertext: str, shift: int) -> str:
    plaintext = ""
    for ch in ciphertext:
        if 'A' <= ch <= 'Z':
            plaintext += chr((ord(ch) - ord('A') - shift + 26) % 26 + ord('A'))
        elif 'a' <= ch <= 'z':
            plaintext += chr((ord(ch) - ord('a') - shift + 26) % 26 + ord('a'))
        else:
            plaintext += ch
    return plaintext

# Main logic
print("********** HASH (Encryption and Decryption) **********")

plaintext = input("\nEnter the plaintext: ")
shift = int(input("Enter the shift value (1-25): "))

ciphertext = encrypt(plaintext, shift)
print("\nEncrypted text:", ciphertext)

decrypted_text = decrypt(ciphertext, shift)
print("Decrypted text:", decrypted_text)
```
## Output:
![image](https://github.com/user-attachments/assets/6e684c3b-9d5b-4b15-88f3-7cf49b61738b)

## Result:
The program is executed successfully.
