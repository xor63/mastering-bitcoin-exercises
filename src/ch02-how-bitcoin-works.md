# 2. How Bitcoin Works

### 2.1 Payment request QR code

Construct a QR code for a payment request with the following details:

* Bitcoin address: "mrCDrCybB6J1vRfbwM5hemdJz73FwDBC8r"
* Amount: "0.00001"
* Label: "Blips and Chitz"
* Message: "Purchase tokens at Blips and Chitz"

Scan the QR code with a QR code reader to verify its contents.

__Reading__: [BIP-21][bip21] is a short proposal that describes the URI scheme
used in payment request QR codes.

### 2.2 Cryptographic hash puzzle

Repeatedly compute the SHA256 hash of the following simplified header (in JSON),
incrementing the nonce in every iteration, until the resulting hash starts with
three consecutive zeros.

```json
{
  "height": 0,
  "version": 1,
  "merkleroot": "4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b",
  "nonce" : 0
}
```

[bip21]: https://github.com/bitcoin/bips/blob/master/bip-0021.mediawiki
