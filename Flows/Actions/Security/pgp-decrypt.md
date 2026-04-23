# PGP Decrypt

## Description

The goal of the process encrypt & sign / decrypt & verify a document is:

1.   The sender is sure that only the recipient can decrypt it.
2.   The recipient can authenticate the document as coming from the sender.

> Note: The signature is optional because a document can be encrypted without a signature. In such a case, there is no verification step.

An overview of the process is shown below:

![Image 5: Pgp Overall Process](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/pgp-overall-process.png)

The **PGP Decrypt** action implements the right part of the process above. It allows a flow to perform a PGP decryption on a string of [ciphertext](https://developer.mozilla.org/en-US/docs/Glossary/Ciphertext). There is also the option to verify the [signature](https://developer.mozilla.org/en-US/docs/Glossary/Signature/Security) for additional authentication.

![Image 6: PGP Decrypt basic configuration](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/pgp-decrypt-configuration.png)

## Usage

The **PGP Decrypt** action converts ciphertext back to plaintext. This makes it possible to retrieve previously encrypted data.

1.   Insert ciphertext data inside _File content_ (you can also insert data referring to a previous step using the [+] **Add** button).
2.   Insert the matching _public_ and _private RSA/PGP key_ (received from a third party service or one that you have previously generated).
3.   If the _private key_ is optionally protected, you must provide the passphrase.

### Supported keys

Extension Kit **supports both RSA** and **PGP keys** for both decrypting and verifying. Note that the key content is shortened for documentation purposes.

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

## Signature (optional)

The **signature verification** authenticates the user by validating the signature using the _public PGP key_ of the message signer. Both RSA and PGP keys are supported for signing.

![Image 7: PGP Decrypt Signature](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/pgp-decrypt-signature.png)

You can Insert a _Signature public key_ by clicking on the corresponding drop down panel.
