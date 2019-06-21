# 4. Keys, Addresses

### 4.1 Generate a private key

Your program should use a cryptographically secure pseudorandom number generator
(CSPRNG) to generate random bits with sufficient entropy (at least 256 bits) and
compute its SHA256 hash. Repeat this process in a loop until the value is less
than the prime p as defined in the secp256k1 standard:

<pre>
    p = FFFFFFFF FFFFFFFF FFFFFFFF FFFFFFFF FFFFFFFF FFFFFFFF FFFFFFFE FFFFFC2F<br>
      = 2<sup>256</sup> - 2<sup>32</sup> - 2<sup>9</sup> - 2<sup>8</sup> - 2<sup>7</sup> - 2<sup>6</sup> - 2<sup>4</sup> - 1
</pre>

Some programming languages may require a bignum library for dealing with very
large numbers.

__Reading__: You may need to read more about entropy to make sure that your
random number has sufficient entropy. Different operating systems have different
sources of entropy.

### 4.2 Confirm point is on the elliptic curve

In the Elliptic Curve Cryptography Explained section of the book, the following
example point P with coordinates (x, y) on the secp256k1 curve is given:

```
P = (55066263022277343669578718895168534326250603453777594175500187360389116729240, 32670510020758816978083085130507043184471273380659243275938904335757337482424)
```

The book then provides a sample Python code to confirm that the point is on the
elliptic curve:

```python
p = 115792089237316195423570985008687907853269984665640564039457584007908834671663
x = 55066263022277343669578718895168534326250603453777594175500187360389116729240
y = 32670510020758816978083085130507043184471273380659243275938904335757337482424
(x ** 3 + 7 - y**2) % p
```

If you're using a different programming language, write a similar program to do
the same. Make sure that your program can handle very large signed integers. The
secp256k1 curve is defined by the following function that you should use in your
program:

<pre>
    y<sup>2</sup> mod p = (x<sup>3</sup> + 7) mod p
</pre>

### 4.3 Generate a public key with OpenSSL

Use the OpenSSL cryptographic library's `EC_POINT_mul()` to generate a public
key. You can use the private key that you have generated in exercise 4.1 or
alternatively, use the example private key from the book:

```
1E99423A4ED27608A15A2616A2B0E9E52CED330AC530EDCC32C8FFC6A526AEDD
```

Use the library's elliptic curve point multiplication to multiply the private
key with the generator point G in order to produce the public key K.

<pre>
    K = k * G
</pre>

Remember that Bitcoin uses a specific elliptic curve and set of constants
defined in a standard called [secp256k1][secp256k1]. From the Standards for
Efficient Cryptography (SEC), the base point G in compressed form is:

```
G = 02 79BE667E F9DCBBAC 55A06295 CE870B07 029BFCDB 2DCE28D9 59F2815B 16F81798
```

and in uncompressed form is:

```
G = 04 79BE667E F9DCBBAC 55A06295 CE870B07 029BFCDB 2DCE28D9 59F2815B 16F81798
       483ADA77 26A3C465 5DA4FBFC 0E1108A8 FD17B448 A6855419 9C47D08F FB10D4B8
```

### 4.4 Convert a public key into a bitcoin address

Using the public key generated from the previous exercise, compute its SHA256
hash and then compute the RIPEMD160 hash of the result to produce a 160-bit
bitcoin address.

<pre>
    A = RIPEMD160(SHA256(K))
</pre>

This double-hash function is called HASH160.

[secp256k1]: https://en.bitcoin.it/wiki/Secp256k1
