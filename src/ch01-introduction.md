# 1. Introduction

### 1.1 Digital signature with OpenSSL

Use the `openssl` command-line tool to create an RSA key pair and to sign and
verify a text file.

1. Prepare an arbitrary text file to be signed.
2. Generate an RSA private key with key length of 2048 bits.
3. Extract the public key from the private key.
4. Sign the text file using SHA256 and your private key, and output a signature
file.
5. Verify the signature of the text file using the public key.

### 1.2 A simple QR code

Use a QR code generator to generate a QR code that simply contains the text
"hi". Identify the different parts of the QR code such as the positioning
markings, the format information, the timing pattern, and so on. If you can,
find where the "h" and "i" is located in the grid of black and white.
