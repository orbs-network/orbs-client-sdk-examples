# Crypto SDK

Crypto SDK is a cross-platform C++ library (with ANSI C exported interfaces) that implements all the necessary cryptographic functions for Orbs clients.

In order to implement some of the functionality, we have elected to use libgcrypt, since it's:

1. Licensed under GNU LGPL v2.1+.
2. FIPS 140 validated.
3. Support FIPS 140-2 mode.

## Functionality

### Build System

Complete cmake setup to build both the crypto-sdk library and its tests (support for both release and debug builds). Prerequisites are defined as `ExternalProject` with either specific git tag clone (`gtest`, and `gmock`) or downloaded from URL with SHA256 verification (`libgpg_error`, and `libgcrypt`.

### Algorithms

#### Hashing

* SHA256
* SHA512
* RIPEMD160

#### Encoding

* BASE58

#### Checksum

* CRC32

### External Dependencies

* Google Test (`gtest`): Google Test is a unit testing library for the C++ programming language, based on the xUnit architecture.
  * Source: [https://github.com/google/googletest.git](https://github.com/google/googletest.git)
  * Version: `release-1.8.0` git tag.
* Google Mock (`gmock`): Google Mock is an extension to Google Test for writing and using C++ mock classes.
  * Source: [https://github.com/google/googletest.git](https://github.com/google/googletest.git)
  * Version: `release-1.8.0` git tag.
* Libgpg-error (`libgpg_error`): Libgpg-error is a small library that originally defined common error values for all GnuPG components.
  * Source: [https://www.gnupg.org/ftp/gcrypt/libgpg-error/libgpg-error-1.27.tar.bz2](https://www.gnupg.org/ftp/gcrypt/libgpg-error/libgpg-error-1.27.tar.bz2)
  * Version: 1.27.
* Libgcrypt (`libgcrypt`): Libgcrypt is a general purpose cryptographic library originally based on code from GnuPG.
  * Source: [https://www.gnupg.org/ftp/gcrypt/libgcrypt/libgcrypt-1.8.2.tar.bz2](https://www.gnupg.org/ftp/gcrypt/libgcrypt/libgcrypt-1.8.2.tar.bz2)
  * Version: 1.8.2.

## Prerequisites

1. [CMake](https://cmake.org)

```bash
brew install cmake
```

## Build

> First, you'd need to run the `./configure.sh` script. It will configure the release build by default, but if you require a debug build, make sure to run it with the `DEBUG` environment variable set:

Release:

```bash
./configure.sh
```

Debug:

```bash
DEBUG=1 ./configure.sh
```

> After the project is configured, you'd need to run the `./build.sh` script:

```bash
./build.sh
```

## Test

> In order to run the tests, you'd need to run the `./test.sh` script:

```bash
./test.sh
```

## Libgcrypt
Libgcrypt is a general purpose cryptographic library originally based on code from GnuPG. It provides
functions for all cryptograhic building blocks: symmetric cipher algorithms (AES, Arcfour, Blowfish, Camellia,
CAST5, ChaCha20 DES, GOST28147, Salsa20, SEED, Serpent, Twofish) and modes (ECB,CFB,CBC,OFB,CTR,CCM,GCM,OCB,
POLY1305, AESWRAP), hash algorithms (MD2, MD4, MD5, GOST R 34.11, RIPE-MD160, SHA-1, SHA2-224, SHA2-256,
SHA2-384, SHA2-512, SHA3-224, SHA3-256, SHA3-384, SHA3-512, SHAKE-128, SHAKE-256, TIGER-192, Whirlpool), MACs
(HMAC for all hash algorithms, CMAC for all cipher algorithms, GMAC-AES, GMAC-CAMELLIA, GMAC-TWOFISH,
GMAC-SERPENT, GMAC-SEED, Poly1305, Poly1305-AES, Poly1305-CAMELLIA, Poly1305-TWOFISH, Poly1305-SERPENT,
Poly1305-SEED), public key algorithms (RSA, Elgamal, DSA, ECDSA, EdDSA, ECDH), large integer functions, random
numbers and a lot of supporting functions.
Libgcrypt works on most POSIX systems and many pre-POSIX systems. It can also be built using a cross-compiler
system for Microsoft Windows.
Libgcrypt can be used independently of GnuPG, but depends on its error-reporting library Libgpg-error.
