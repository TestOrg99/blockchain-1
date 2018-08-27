# Part5
------
## Bitcoin Address
Bitcoin addresses are public. If you want to send coins to someone, you need to know their address. Bitcoin relies on a combination of cryptography algorithms to create the private and public keys, and guarantee that no one else in the world can access your coins without getting physical access to your keys.
## Public-key Cryptography
Public-key cryptography algorithms use pairs of keys: public keys and private keys. Public keys are not sensitive and can be disclosed to anyone. In contrast, private keys shouldn’t be disclosed: no one but the owner should have access to them because it’s private keys that serve as the identifier of the owner. 
In mathematics and cryptography, there’s a concept of digital signature – algorithms that guarantee:
1)that data wasn’t modified while being transferred from a sender to a recipient;
2)that data was created by a certain sender;
3)that the sender cannot deny sending the data.
Digital signatures are not encryption, you cannot reconstruct the data from a signature.  The difference between signatures and hashes is key pairs: they make signature verification possible.Every transaction in Bitcoin must be verified before being put in a block. Verification means (besides other procedures):
1)Checking that inputs have permission to use outputs from previous transactions.
2)Checking that the transaction signature is correct.
```sh

```
