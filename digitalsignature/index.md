# DIGITAL SIGNATURE
#### Veren Iliana - 5/26/2017


Digital signature is a cryptographic value that is calculated from the data and a secret key known only by the signer. Digital signatures are based on public key cryptography, also known as asymmetric cryptography. The digital equivalent of a handwritten signature or stamped seal, but offering far more inherent security. As with conventional handwritten signatures, only the person who creates a digital message must be capable in generating a valid signature. The basic idea is that the person who signs the message uses a private key, and the receiving party uses the matching public key.

> In many countries, including the United States, digital signatures have the same legal significance as the more traditional forms of signed documents. The United States Government Printing Office publishes electronic versions of the budget, public and private laws, and congressional bills with digital signatures.

Digital signatures are one of the most important cryptographic tools and are widely used today. Most modern email programs support the use of digital signatures and digital certificates, making it easy to sign any outgoing emails and validate digitally signed incoming messages. Digital signatures are also used extensively to provide proof of authenticity, data integrity and non-repudiation of communications and transactions conducted over the Internet.

## HOW IT WORKS

Using a public key algorithm, one can generate two keys that are mathematically linked: one private and one public. To create a digital signature, signing software (such as an email program) creates a one-way hash of the electronic data to be signed. The private key is then used to encrypt the hash. The encrypted hash -- along with other information, such as the hashing algorithm -- is the digital signature. 

The reason for encrypting the hash instead of the entire message or document is that a hash function can convert an arbitrary input into a fixed length value, which is usually much shorter. Let us assume RSA is used as the signing algorithm. The encryption/signing process using RSA involves modular exponentiation. Signing large data through modular exponentiation is computationally expensive and time consuming. The hash of the data is a relatively small digest of the data, hence signing a hash is more efficient than signing the entire data.

The value of the hash is unique to the hashed data. Any change in the data, even changing or deleting a single character, results in a different value. This attribute enables others to validate the integrity of the data by using the signer's public key to decrypt the hash. If the decrypted hash matches a second computed hash of the same data, it proves that the data hasn't changed since it was signed. If the two hashes don't match, the data has either been tampered with in some way (integrity) or the signature was created with a private key that doesn't correspond to the public key presented by the signer (authentication).

![Digital Signature Scheme](https://vereniliana.github.io/digitalsignature/ds_pic.jpg)

The following points explain the entire process in detail
*	Each person adopting this scheme has a public-private key pair.
*	Generally, the key pairs used for encryption/decryption and signing/verifying are different. The private key used for signing is referred to as the signature key and the public key as the verification key.
*	Signer feeds data to the hash function and generates hash of data.
*	Hash value and signature key are then fed to the signature algorithm which produces the digitally signed document. Signature is appended to the data and then both are sent to the verifier.
*	Verifier feeds the digital signature and the verification key into the verification algorithm. The verification algorithm gives some value as output.
*	Verifier also runs same hash function on received data to generate hash value.
*	For verification, this hash value and output of verification algorithm are compared. Based on the comparison result, verifier decides whether the digital signature is valid.
*	Since digital signature is created by ‘private’ key of signer and no one else can have this key; the signer cannot repudiate signing the data in future.

## IMPORTANCE OF DIGITAL SIGNATURE

Out of all cryptographic primitives, the digital signature using public key cryptography is considered as very important and useful tool to achieve information security.
Apart from ability to provide non-repudiation of message, the digital signature also provides message authentication and data integrity. Let us briefly see how this is achieved by the digital signature 
*	**Message authentication** − When the verifier validates the digital signature using public key of a sender, he is assured that signature has been created only by sender who possess the corresponding secret private key and no one else.
*	**Data Integrity** − In case an attacker has access to the data and modifies it, the digital signature verification at receiver end fails. The hash of modified data and the output provided by the verification algorithm will not match. Hence, receiver can safely deny the message assuming that data integrity has been breached.
*	**Non-repudiation** − Since it is assumed that only the signer has the knowledge of the signature key, he can only create unique signature on a given data. Thus, the receiver can present data and the digital signature to a third party as evidence if any dispute arises in the future.
By adding public-key encryption to digital signature scheme, we can create a cryptosystem that can provide the four essential elements of security namely − Privacy, Authentication, Integrity, and Non-repudiation.



### References
[http://www.cryptography-textbook.com/](http://www.cryptography-textbook.com/)
[https://www.tutorialspoint.com/cryptography/cryptography_digital_signatures.htm](https://www.tutorialspoint.com/cryptography/cryptography_digital_signatures.htm)
[http://searchsecurity.techtarget.com/definition/digital-signature](http://searchsecurity.techtarget.com/definition/digital-signature)


<div style="text-align: right"> 
[<img src="https://vereniliana.github.io/digitalsignature/Home.png" width="48">](https://vereniliana.github.io)
</div>
