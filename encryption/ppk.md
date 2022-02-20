[back](encryption.md)

# Public Private Key Encryption

## Asymmetric Encryption

A user generates an RSA key pair - basically 2 encryption keys with a subtle
relationship, whereby anything encrypted with one key can be decrypted with the
other, and vica-versa.

One key is made public, shared with the world, the other is kept private, known
only to the user.  That last part is extremely important, as should the private
key become known to anyone/thing else then the security of the key pair is
compromised and they should be discarded and new ones generated.

## Bob and Alice

![Bob chats to Alice](images/pubprivenc.png)

1. Bob wants to send a message, "Hello Alice", to Alice.
2. He encrypts the message using Alice's public key.
3. He sends the encrypted message over the insecure network to Alice.
4. Alice receives the message and decrypts it using her private key, "Hello
   Alice"

## Signatures

When using other forms of encryption (or even in-clear messaging) a signature of
the message can be generated [(see hashing functions in
wikipedia)](https://en.wikipedia.org/wiki/Hash_function) that is composed of the
message text and encrypted with the *private* key of the sender.

The receiver receives the message (unencrypted) and a signature blob, normally
'base64` encoded for safe transmission over email.  She decodes the base64
encoding and verifies the signature with the original message using the senders
*public* key. Should the signature pass verification then the receiver knows
that the original message did come from the sender, the only holder of the
private key, and that it has not been tampered with.

![Bob signs his message](images/signing.png)

1. Bob creates his message in the file `message.txt`
2. Using his private key he creates a signature of that message.txt file
   `openssl dgst -sha256 -sign bob.id_rsa -out signature message.txt`
3. The signature, being a pure binary file, should be encoded for transmission
   using the `base64` utility.
   `base64 signature >signature.b64`
4. Bob sends both the `message.txt` and the encoded `signature.b64` file to
   Alice.
5. Alice can open the `message.txt` as it is unencrypted, plain text.  Now she
   wants to ensure that it came from Bob and has not been tampered with.
6. Alice decodes the `signature.b64` file into a `signature` file.
   `base64 --decode signature.b64 >signature`
7. Alice checks the signature did indeed come from Bob using his public key.
   `openssl dgst -sha256 -verify bob.id_rsa.pub -signature signature message.txt`
8. The signature is confirmed, the message can only have come from Bob as it was
   signed with his private key, moreover, Alice can be sure that no-one has
   tampered with it.


## GPG (PGP)

[GPG (GNU Privacy Guard)](https://gnupg.org/https://gnupg.org/) based on [Phil
Zimmerman's](https://philzimmermann.com/EN/background/index.html) PGP (Pretty
Good Privacy) - I'll link to [openpgp](https://www.openpgp.org/) as I can't find
the original, is one use of PPK encryption.  The private key is called the
Secret Key in GPG and the public part is called the GPG public key.  Using GPG
you can encrypt messages, blocks of text or even whole files (or collections of
files as in zips and tar files).  Using the recipients public key  to encrypt
the message ensures that only they can decrypt it (using their private or secret
key).

GPG extends this a little further, by using 'Slot' encryption (my term, I have
no idea what the correct mathematical terminology is, this [Stack
Overflow](https://stackoverflow.com/questions/38846/how-to-encrypt-one-message-for-multiple-recipients)
answer may take you on that journey) allows you to encrypt the same message for
numerous recipients at the same time, such that each one will be able to decrypt
it using their specific private key.

[back](encryption.md)
