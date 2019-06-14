# 1. Introduction

### 1.1 Digital Signature with OpenSSL

Use the `openssl` command-line tool to create an RSA key pair and to sign and
verify a text file.

1. Prepare an arbitrary text file to be signed.
2. Generate an RSA private key with key length of 2048 bits.
3. Extract the public key from the private key.
4. Sign the text file using SHA256 and your private key, and output a signature file.
5. Verify the signature of the text file using the public key.
