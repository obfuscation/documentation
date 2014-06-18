The Seattle Protocol is an encryption and authentication layer for use by obfuscated
protocols.

Introduction

Obfuscated protocols use novel ways to encode travel so that it can bypass filters,
but they also share some common requirements. Encryption and aunthenticaiton is one
such common need. There are generally two approaches to providing these properties:
roll your own or use TLS. TLS is not a perfect fit, and so developers sometimes
rolle their own protocols. The Seattle Protocol offers a third option: a layer which
provides encryption and authentication and which has been developed by the community to
meet the specific needs of the obfuscation community.

Why not just use TLS?

TLS is general purpose solution for all of the Internet's encryption and aunthetication
needs. There are trade-offs in being a general purpose solution. The Seattle Protocol
aims to better fit for obfuscating protocols.

Design Requirements

The key requirement of an encryption and authentication layer for use in obfuscating
protocols is that all output from the encryption and authentication later is
indistuishable from randomness. Therefore all ouptut must be either a single use
random value or encrypted data. There is no plaintext handshake.

A popular choice in the obfuscation community is the ntor protocol, specifically with
Curve25519 public keys. As these are not fully random, Elligator compression is used.
While this form of key exchange is emerging as a standard choice, it only provides
key exchange and does not specify a cipher, cipher mode, or method of authenticating
the data stream. The format of records within the data stream are also not specified.
The Seattle Protocol will build on the previous work on obfuscating protocols by
providing reasonablely safe choices for the key exchange, cipher and mode, and
authentication method.

Another design requirement is simplicity. It is not the goal of this project to provide
for all use cases wherein encryption and/or authentication can be used on the Internet.
The goal is to provide a reusable component for obfuscating protocols, with a clearly
defined specification and implementations in multiple languages. Rather than allowing
for extensive configurability and customization, reasonable defaults will be chosen.
This reduces implementaiton risk for the user as there is no configuration options and
therefore reduced possibilities for unsafe use. However, use with a secure and not
broken PRNG is recommended.

The implementations should be kept brief and reduce dependencies on third party
libraries in order to maintain auditability.

Protocol Specification

Key Exchange - ntor with Curve25519/Elligator
Cipher - AES in counter mode with "encrypt then HMAC" or Salsa with "encrypt then HMAC"
HMAC - Sha256 or Sha3

Record format - Encrypted length, Encrypted data, HMAC

Format

Ephemeral Public Key
Authentication Code
IV
Record
...
Record

Record Format

Length
Payload

Payload Format

Encrypted Data
HMAC

Related Work

QUIC
MinimalLT
CurveCP
Noise
TLS 1.3
Stegotaurus

Open Issues

Replay Attacks
Stream fragmentation
Length padding
Truncation attacks
Choice of a good PRNG

References

ntor
Curve25519
Ed25519
Elligator
AES
Salsa
Encrypt then MAC
