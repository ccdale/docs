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
size of 128 bits still gives a theoretical brute force time measured in billions
of years to crack AES.


![AES Grid](../images/aesgrid.png)

AES performs a number of encryption rounds, each one consisting of key
insertion, substitution, permutation to shift rows in the grid, permutation to
mix columns in the grid and finally add the round key.

The last round does everything above except mix columns.

The number of rounds depends on the key size. 128 bits = 10 rounds, 192 = 12
rounds and 256 = 14 rounds.

[back](index.md)
