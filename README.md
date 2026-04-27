# OpenSSL Lab: Encrypting and Decrypting Data

## Goal
Use OpenSSL to encrypt and decrypt data from the command line and understand the difference between encrypted binary output and Base64-encoded encrypted text.

## Tools Used
- Security Workstation VM
- OpenSSL
- Linux terminal

## What I Did
- Navigated to the lab support directory containing the plaintext file
- Viewed the original contents of `letter_to_grandma.txt`
- Encrypted the file using AES-256-CBC with OpenSSL
- Observed that the encrypted output did not display as normal readable text when viewed directly
- Re-ran the encryption using the `-a` option to Base64-encode the ciphertext
- Viewed the Base64-encoded encrypted output in the terminal
- Decrypted the encrypted file back into plaintext using OpenSSL

## Commands Used
```bash
cd ./lab.support.files/
cat letter_to_grandma.txt
openssl aes-256-cbc -in letter_to_grandma.txt -out message.enc
cat message.enc
openssl aes-256-cbc -a -in letter_to_grandma.txt -out message.enc
cat message.enc
openssl aes-256-cbc -a -d -in message.enc -out decrypted_letter.txt
cat decrypted_letter.txt


```
-## What I Observed

When the file was first encrypted without Base64 encoding, the output appeared as unreadable binary data in the terminal.

After running the command again with the `-a` option, the encrypted output appeared as readable ASCII text made up of letters, numbers, and symbols. The data was still encrypted, but Base64 encoding made it easier to display and handle in text form.

After decryption, the original plaintext message was restored successfully.

## Why It Matters

This lab reinforced several important security concepts:

- Encryption transforms readable plaintext into protected ciphertext
- Encrypted binary data does not display cleanly in a terminal
- Base64 encoding makes encrypted data easier to copy, display, and store in text-based systems
- Correct decryption requires the same password and the proper decoding options

In a cybersecurity role, understanding how encryption tools work from the command line is useful for:

- secure data handling
- understanding encrypted output formats
- recognizing the difference between encryption and encoding
- working with foundational cryptographic tools in Linux environments

## Key Takeaway

This lab showed how OpenSSL can be used to encrypt and decrypt files with AES-256-CBC, and why Base64 encoding is useful when encrypted data needs to be displayed or transported in text form.
