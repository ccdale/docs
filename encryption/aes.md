[back](index.md)

# Advanced Encryption Standard

After a competition to find a 'good enough' encryption standard the Rijndael
Cypher was chosen to become the Advanced Encryption Standard.

AES is a 128 bit symmetric block cypher, which means that the incoming message
is split up into blocks of 128 bits.  Each of those blocks are then operated on
and the resulting output cypher text is also 128 bits long. i.e. the encrypted
message size is normally the same size as the input message.

The key size for AES is 128, 192 or 256 bits in length, which will give
increasing levels of security at the cost of processing time. The smallest key
size of 128 bits still gives a theoretical brute force time measured in 1000s of
years.

All operations in AES are performed on a block of 128 bits arranged as a grid of
16 bytes.

![AES Grid](../aesgrid.png)

[back](index.md)
