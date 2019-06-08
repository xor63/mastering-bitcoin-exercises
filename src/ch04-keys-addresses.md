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
