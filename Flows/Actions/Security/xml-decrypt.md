# XML Decrypt

## Description

The **XML Decrypt** action applies an [XML decryption](https://www.w3.org/TR/xmlenc-core1/) to [XML formatted data](https://www.w3.org/standards/xml/core#summary) that has been encrypted.

The counterpart of this XML Decrypt action is the [XML Encrypt](https://docs-external.u4pp.com/extensions-kit/built-in-actions/xml-encrypt/).

## Usage

![Image 3: Xml Decrypt basic configuration](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xml-decrypt-configuration.png)

The user must fulfill those fields:

1.   A `Client certificate` is required and it must be a certificate with a RSA Private key.

2.   (Optional) The `Use Web Service Security OASIS Standard`is an optional flag that can be set to indicate we want to decrypt a SOAP XML by using the Web Service Security (WSS) OASIS protocol. More detail here about [OASIS Standard Specification](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf). When unchecked, a basic decryption is performed according to [W3C Recommendation](https://www.w3.org/TR/xmlenc-core/#sec-Processing-Decryption).

3.   The `XML content` can either contain an actual XML string or a reference to an XML output of a previous step by using the [+] button.
