# 5. Wallets

### 5.1 Generate mnemonic words

Write a program to generate and print mnemonic words from a given random
sequence of bits.

1. Create a random sequence (entropy) of 128/160/192/224/256 bits.
2. Compute the SHA256 hash of the random sequence. Take the first
(entropy-length/32) bits of its hash as the checksum.
3. Concatenate the random sequence and the checksum.
4. Divide the result into sections of 11 bits.
5. Map each 11-bit value to a word from the predefined dictionary of 2048 words.
6. Print the mnemonic words in the correct order.

Table 5-1: Checksum bits and number of mnemonic words depend on length of
entropy.

| Entropy (bits) | Checksum (bits) | Mnemonic length (words) |
| :---:          | :---:           | :---:                   |
| 128            | 4               | 12                      |
| 160            | 5               | 15                      |
| 192            | 6               | 18                      |
| 224            | 7               | 21                      |
| 256            | 8               | 24                      |

Get the dictionary/wordlist from [BIP-39][bip39]. There's a section that
describes the characteristics of an ideal wordlist, and a separate section that
links to the actual wordlists.

[bip39]: https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki
