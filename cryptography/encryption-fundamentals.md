## Encryption Fundamentals

Encryption protects data by transforming readable information into ciphertext
that can only be reversed using the correct key.

Encryption is a **two-way** process and is essential for data confidentiality.

---

## Symmetric Encryption

Uses the same key to encrypt and decrypt data.

### Characteristics
- Fast
- Efficient for large data
- Requires secure key sharing

### Common use cases
- Disk encryption
- VPNs
- WiFi security
- TLS data sessions

### Algorithms
- AES (modern, secure standard)
- DES (deprecated)
- 3DES (outdated and slow)

---

## Asymmetric Encryption

Uses two keys:
- Public key (encrypt)
- Private key (decrypt)

### Characteristics
- Slower than symmetric encryption
- Solves key distribution problem

### Use cases
- HTTPS
- Digital signatures
- Identity verification
- Secure key exchange

### Algorithms
- RSA (older, reliable, slower)
- ECC (modern, efficient, smaller keys)

---

## Block Cipher Modes

Block ciphers encrypt fixed-size blocks.
Cipher modes define how blocks are combined.

### CBC (Cipher Block Chaining)
- Chains encrypted blocks together
- Vulnerable to padding oracle attacks
- Not recommended for modern systems

### GCM (Galois/Counter Mode)
- Provides confidentiality and integrity
- Authenticated encryption
- Standard for modern TLS

---

## Summary
- Symmetric encryption protects bulk data
- Asymmetric encryption enables secure key exchange
- Modern systems combine both for security
