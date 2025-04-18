### Symmetric Encryption
Symmetric encryption uses a single key for both encryption and decryption and the same key is shared between the sender and receiver. 
##### Mechanism:
The secret symmetric key is shared with the receiver using some form of method. 

The sender encrypts the plain-text data to be transmitted using the secret key and transmits the cipher-text data to the receiver, which will in turn decrypt the cipher-text using the secret key.

##### Examples:
- AES (Advanced Encryption Standard)
- ChaCha20 (Modern & Fast encryption)

* * *
### Asymmetric Encryption
Asymmetric Encryption makes use of public and private keys for decrypting and encrypting data respectively. 
#### Privacy & Integrity
**Privacy** is about ensuring that data transmitted can only be decrypted with the right key by the receiver.
**Integrity** is about whether the receiver can determine whether data received is actually from the receiver, and uses **signatures** for this.
##### Mechanism:
1) The sender and receiver generate their corresponding private-public key pair before sending the public keys to one another.
2) The sender will encrypt the message to be sent using the **receiver's public key** and will add a **digital signature**(encrypted data for authenticating sender) to the encrypted message using its private key.
3) The receiver will then use the sender's public key to verify the signature and use its own private key to decrypt the message.

#### Examples:
- RSA
- Diffie-Hellman

#### Note:
Adding the signature can occur before or after encryption provided that the encryption/verifying signature steps are changed accordingly.

* * *
### Hashing
Hashing is a one-way process that converts input data into a fixed-size string of characters, called a **hash value** and unlike encryption, hashing is not reversible.
##### Use Cases:
- Verifying data integrity (Detecting whether a file has been tampered with)
- Storing passwords securely 
- Digital Signatures

##### Examples:
- SHA-256
- bcrypt (slower, more bruteforce resistant)