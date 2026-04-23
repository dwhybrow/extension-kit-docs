# PGP Encrypt

## Description

The goal of the process encrypt & sign / decrypt & verify a document is:

1.   The sender is sure that only the recipient can decrypt it
2.   The recipient can authenticate the document as coming from the sender, which is also the signer.

> Note: The signature is optional because a document can be encrypted without a signature. In such a case, there is no verification step.

An overview of the process is shown below:

![Image 5: Pgp Overall Process](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/pgp-overall-process.png)

The **PGP Encrypt** action implements the left part of the process above. It allows a flow to perform a [PGP encryption](https://www.fortinet.com/resources/cyberglossary/pgp-encryption) on a string of [plaintext](https://developer.mozilla.org/en-US/docs/Glossary/Plaintext). There is also the option to add a [signature](https://developer.mozilla.org/en-US/docs/Glossary/Signature/Security) for additional authentication.

![Image 6: PGP Encrypt basic configuration](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/pgp-encrypt-configuration.png)

## Usage

The **PGP Encrypt** action converts plaintext to [ciphertext](https://developer.mozilla.org/en-US/docs/Glossary/Ciphertext), always encasing it in an ASCII armor so it can be sent through standard messaging, for example, email. This makes it possible to send data securely to third-party services.

1.   Insert plaintext data inside _file content_ (you can also insert data referring to a previous step by clicking the [+] **Add** button).
2.   Insert a _public RSA/PGP key_ of choice (received from a third party service or one that you have generated).
3.   Select the _cipher algorithm_ of choice (CAST5, BLOWFISH or AES-256).

### Supported Keys

Extension Kit **supports both RSA** and **PGP keys** for both encrypting and signing. Note that the key content is shortened for documentation purposes.

> Keys must be used as they are generated, with no modifications done in them to avoid faulty keys.

**Example of _Public RSA key_:**

```
-----BEGIN PUBLIC KEY-----
j+TgseJangU6imik5mL0qYg9523FcukXfS9MH+qgisF1DotW1C9BADUKd0okqWUZ [...]
-----END PUBLIC KEY-----
```

**Example of _Private RSA key_:**

```
-----BEGIN RSA PRIVATE KEY-----
MIIJKAIBAAKCAgEAkx8U2Yv7KUQbzspGzcNv/s8SY168tVK55HjG/lKDaBi0SWPi [...]
-----END RSA PRIVATE KEY-----
```

**Example of _Public PGP key_:**

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: Keybase OpenPGP v1.0.0
Comment: https://keybase.io/crypto

xsFNBGMz9zABEADLYAjUH0+kZQtjMuDcZ3r4+IarVQRT+4+nFgMOZd1T+Laomz24 [...]

-----END PGP PUBLIC KEY BLOCK-----
```

**Example of _Private PGP key_:**

```
-----BEGIN PGP PRIVATE KEY BLOCK-----
Version: Keybase OpenPGP v1.0.0
Comment: https://keybase.io/crypto

xcaGBGMz9zABEADLYAjUH0+kZQtjMuDcZ3r4+IarVQRT+4+nFgMOZd1T+Laomz24 [...]

-----END PGP PRIVATE KEY BLOCK-----
```

> Note: The type of key being used is automatically determined by the system. User action is not required.
> 
> 
> **NOTE**: The document is also **compressed** with basic ZIP algorithm before being encrypted. As an example with the encryption of a big 20MB XML file, the result is a 2.5MB PGP message.

## Signature (optional)

The **signature** authenticates the user. Both RSA and PGP keys are supported for signing.

![Image 7: PGP Encrypt signature](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/pgp-encrypt-signature.png)

1.   Select one of the provided _hash algorithms_ (MD2, MD5, RIPE-MD/160, SHA-1, SHA-224, SHA-256, SHA-384, SHA-512).
2.   Optionally select the _Encrypt and sign in one pass_ checkbox if you want to encrypt and sign the document in _one pass_. If unchecked, the encrypt and sign proceeds in _two passes_: first sign the document, and second, encrypt the signed document.
3.   Insert a matching _Signature private key_ and _Signature public key_.
4.   If the _Signature private key_ is optionally protected, you must provide the passphrase.
