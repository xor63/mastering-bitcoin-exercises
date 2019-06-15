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

__Reading__: You may need to read more about entropy to make sure that your random
number has sufficient entropy. Different operating systems have different
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
