# DES - Data Encryption Standard
## Stream Cipher

- A stream cipher = cipher that encrypts a digital data stream one bit or one byte at a time
- is unbreakable IF the cryptographic keystream is truly random and used only once = **one time pad**
- for practical reasons: 
  - bit-stream generator must be implemented as an algorithmic procedure = **pseudo-random**
  - key/seed-controlled: 2 users only need to share the generating key to each produce the keystream


## Block Cipher
- A block cipher = cipher in which a **block of plaintext** is treated as a whole and used to produce a **ciphertext block of equal length**
- typical block size: 64/128 bits
- uses a **symmetric encryption key**
- can be used to achieve the same effect as a stream cipher using some modes of operation

## Stream and Block Cipher

-  Initialization Vector: 
   -  used so that identical plaintext will not result in same ciphertext later (comparable to salt)
   - not secret
   - sent in plain text

## Feistel Cipher
- proposed the use of:
  - **Substitution**: each plaintext element or group of elements is replaced by a corresponding ciphertext element or group of elements
  - **Permutation**: A sequence of plaintext elements is replaced by a permutation of that sequence. No elements are added or replaced, rather the order in which they appear changes

- practical application of proposal by Claude Shannon (confusion and diffusion)

## Diffusion and Confusion
- introduced by Claude Shannon
- concern: thwart cryptanalysis based on statistical analysis 
- 2 methods of frustrating statistical cryptanalysis:
  - diffusion: each ciphertext is affected by many plaintext digits
  - confusion: complex substitution algorithm

### Obtaining Diffusion and Confusion
- Diffusion is clearly not obtained by substitution because statistical 
relationships in the plaintext can be found in the ciphertexts. 
- Think of a simple Caesar substitution. 
- **Diffusion** is obtained by **permutation**.
- **Confusion** is obtained through **substitution**. 


- A stream cipher has no permutation
- Stream ciphers score low on diffusion

## Feistel Cipher structure

- Rounds of a Feistel Cipher:
  - substitution is performed on left half of the data
    - applying a roudn function F to the right half
    - XOR output of that function and the left half of the data

  - permutation is performed of the interchange of the 2 halves of the data (= SPN substitution-permutation network)

## Feistel Cipher Design Features

- Block size:
  - Larger blocks = increased security, but reduced encryption/decryption speed
- Key size:
  - Larger key = greater security but may decrease encryption/decryption speed 
- Number of rounds:
  - single round = inadequate
  - more rounds = more secure
  - typical size = 16 rounds
- Subkey generation algorithm or key schedule algorithm
  - greater complexity = greater difficulty of cryptanalysis
- Round function F
  - greater complexity = greater difficulty of cryptanalysis
- Fast software encryption/decryption
- ease of analysis
  - as difficult as possible to cryptanalyze, but you cant analyze the strenghts and weaknesses and even vulnerabilities if it's too difficult

## Feistel Example

- Feistel Decryption = same as encryption, but uses subkeys in revers order

## DES (Data Encryption Standard) 
- 

  