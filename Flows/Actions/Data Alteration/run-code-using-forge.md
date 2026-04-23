# Run Code action using Forge library for cryptography requirements

You can use the tools provided by the Forge library, to use the **Run Code** action for specific cryptography requirements that cannot be fulfilled by the existing Extension Kit actions, such as PGP Encrypt, PGP Decrypt, Sign XML and Verify XML. Some guidelines and examples are provided below.

## Forge library

The [Forge library](https://digitalbazaar.github.io/forge/) is a fully native implementation of the TLS protocol in JavaScript. Therefore, it can be used as a complete toolbox for cryptography requirements, such as PKI methods, various classic algorithms, ciphers methods, message digests methods, as well as many useful security utilities.

### Private Key Infrastructure (PKI) methods

For details on Forge PKI methods, see [Forge PKI](https://digitalbazaar.github.io/forge/#pki-1).

For an example of how to use the `forge.pki` object, see [Sign a SHA256 digest and base64-encode it](https://docs-external.u4pp.com/extensions-kit/built-in-actions/run-code-using-forge/#sign-a-sha256-digest-and-base64-encode-it).

### Ciphers methods

For details on Forge Ciphers methods, see [Forge Ciphers](https://digitalbazaar.github.io/forge/#ciphers-1).

For an example of how to use the `forge.cipher` object, see [Cipher and Decipher using AES algorithm](https://docs-external.u4pp.com/extensions-kit/built-in-actions/run-code-using-forge/#cipher-and-decipher-using-aes-algorithm).

### Message Digests methods

For details on Forge message digests methods, see [Forge Message Digests](https://digitalbazaar.github.io/forge/#message-digests-1).

For an example of how to use the `forge.md` object, see [Calculate a SHA256 hash and base64-encode it](https://docs-external.u4pp.com/extensions-kit/built-in-actions/run-code-using-forge/#calculate-a-sha256-hash-and-base64-encode-it).

### Utilities

For details on Forge utilities, see [Forge Utilities](https://digitalbazaar.github.io/forge/#utilities-1).

Examples are provided below showing how to use the `forge.util` object.

**Sign a SHA256 digest and base64-encode it**

Here is an example of how to:

1.   Calculate the SHA256 of a given XML content.

2.   Sign the digest result with a given private key in PEM format.

> Note: The private key PEM content must not contain line breaks. You must remove the line breaks or provide a JavaScript function to do it.

3.   Base64-encode the signature and return it.

```js
// build private key base on private_key given as a RunCode action parameter in PEM format (without line break)
const privateKey = forge.pki.privateKeyFromPem(private_key);

// build sha256 to digest the given XML content
const md = forge.md.sha256.create();
md.update(xmlFileToSign);

// calculate the signature of the sha256 digest with the given private key
const signature = privateKey.sign(md);

// base64-encode the signature and return it
const signatureb64 = forge.util.encode64(signature);

return signatureb64;
```

**Verify the signature**

In this example, the goal is to verify the signature of the given content against the given public key.

The given content is contained in the variable `xmlFileUsedForSign` and the public key corresponds to the private key used to generate the signature.

> Note: In the example, the given signature to be verified is a base64-encoded string, therefore, it must first be decoded before being used by the `verify` function.

```js
var publicKeyString = `
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAvETp1ldcd3gFwTlFBgQL
...
...
2wIDAQAB
-----END PUBLIC KEY-----
`;
var publicKey = forge.pki.publicKeyFromPem(publicKeyString);;

var md = forge.md.sha256.create();
md.update(xmlFileUsedForSign, 'utf8');

var signatureToVerify = forge.util.decode64(signatureB64ToVerify);

var verified = publicKey.verify(md.digest().bytes(), signatureToVerify);

return verified;
```

**Calculate a SHA256 hash and base64-encode it**

In this example, the SHA256 hash of a given XML content is calculated, and then base64-encoded.

```js
// calculate the SAH256 of the given XMLContent
const md = forge.md.sha256.create();
md.update(xmlContent);

// Base64-encode the bytes of the digest
const xmlContentEnc64 = forge.util.encode64(md1.digest().bytes());

return xmlContentEnc64;
```

**Calculate the HMAC SHA1 of a content and base64-encode it**

In this example, the goal is to calculate the HMAC of a content using a SHA1 hash function and extract the bytes of the hexadecimal result in order to base64-encode it.

```js
// Initilize the HMAC object with the given secretKey and the contentToSign
var hmac = forge.hmac.create();
hmac.start('sha1', secretKey);
hmac.update(contentToSign);

// base64-encode the hexadecimal HMAC SHA1 result
var result_toHex = hmac.digest().toHex();
var bytes = forge.util.hexToBytes(result_toHex)
var result_bytes_b64 = forge.util.encode64(bytes);

return result_bytes_b64;
```

**Cipher and Decipher using AES algorithm**

This example shows how to cipher and then decipher a file content.

```js
// generate a random key and IV
// Note: a key size of 16 bytes will use AES-128, 24 => AES-192, 32 => AES-256
var key = forge.random.getBytesSync(16);
var iv = forge.random.getBytesSync(16);

// encrypt some bytes using CBC mode (other modes include: CFB, OFB, CTR, and GCM)
var cipher = forge.cipher.createCipher('AES-CBC', key);
cipher.start({iv: iv});
cipher.update(forge.util.createBuffer(FileContent));
cipher.finish();
var encrypted = cipher.output;

// decrypt some bytes using CBC mode (other modes include: CFB, OFB, CTR, and GCM)
var decipher = forge.cipher.createDecipher('AES-CBC', key);
decipher.start({iv: iv});
decipher.update(encrypted);
decipher.finish();

return decipher.output;
```

#### More examples

The above examples cover some of the most common and useful applications of the tools offered by _Forge_. You can find a more exhaustive collection in the [Forge documentation](https://digitalbazaar.github.io/forge/#documentation).
