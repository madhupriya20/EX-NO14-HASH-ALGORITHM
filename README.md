# EX-NO14-HASH-ALGORITHM

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
# Function to compute a simple hash using XOR and addition
def compute_simple_hash(message):
    temp = 0
    
    for ch in message:
        temp = temp ^ ord(ch)       # XOR each character
        temp = (temp + ord(ch)) % 256   # Add character value (limit to 1 byte)
    
    return temp


# Step 1: Input the message
message = input("Enter the message: ")

# Step 2: Compute the hash
hash_value = compute_simple_hash(message)

# Step 3: Display the computed hash in hexadecimal
print("Computed Hash (in hex):", format(hash_value, "02x"))

# Step 4: Verify the hash
received_hash = input("Enter the received hash (in hex): ")

received_hash_value = int(received_hash, 16)

# Step 5: Compare hashes
if hash_value == received_hash_value:
    print("Hash verification successful. Message is unchanged.")
else:
    print("Hash verification failed. Message has been altered.")
```


## Output:
<img width="445" height="120" alt="image" src="https://github.com/user-attachments/assets/18282a15-0932-4393-bf26-3d71ef403183" />


## Result:
The program is executed successfully.
