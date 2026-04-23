# XML Encrypt 

## Description

The **XML Encrypt** action applies an [XML encryption](https://www.w3.org/TR/xmlenc-core1/) to [XML formatted data](https://www.w3.org/standards/xml/core#summary).

This action is based on a **RSA asymmetric cipher** with public and private keys pairs. Typically, this action encrypts XML content with the public key of the recipient, so that the recipient is the only one which can decrypt it with its matching private key.

The counterpart of this XML Encrypt action is the [XML Decrypt](https://docs-external.u4pp.com/extensions-kit/built-in-actions/xml-decrypt/).

## Usage

![Image 1: Xml Encrypt basic configuration](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xml-encrypt-configuration.png)

The user must fulfill those fields:

1.   A `Client certificate` is required and it must be a certificate with a RSA Public key.

2.   The `Element to encrypt` indicates the XML element that must be encrypted within the entire given XML content. This field is optional. Note that if _element to encryt_ is empty, the action will just encrypt the entire XML string given in `XML content` field, or the first child of the SOAP Body when using Web Service Security (WSS) OASIS Standard.

3.   (Optional) The `Use Web Service Security OASIS Standard`is an optional flag that can be set to indicate we want to encrypt a SOAP XML by using the Web Service Security (WSS) OASIS protocol. More detail here about [OASIS Standard Specification](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf). When unchecked, a basic encryption is performed according to [W3C Recommendation](https://www.w3.org/TR/xmlenc-core/).

4.   The `XML content` can either contain an actual XML string or a reference to an XML output of a previous step by using the [+] button.

## Basic XML encryption

The **basic** encryption is performed when the `Use Web Service Security OASIS Standard` remains unchecked and is done according to [W3C Recommendation](https://www.w3.org/TR/xmlenc-core/).

Example: given the following `XML content`:

```
<?xml version="1.0" encoding="utf-8"?>
<transferPayment>
    <paymentMessage>
        <format>ISO20022</format>
        <mimeType>text/xml</mimeType>
        <compressed>0</compressed>
        <content>PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTE2Ij8+PERvY3VtZW50IHhtbG5zOnhzaT0iaHR0cDo==</content>
    </paymentMessage>
</transferPayment>
```

> **NOTE**: If the `Element to encrypt`field is empty, the XML Encrypt action will encrypt the whole XML content.

In the case that the `Element to encrypt` field contains the value "_paymentMessage_" then the result will look like that:

```
<?xml version="1.0" encoding="utf-8"?>
<transferPayment>
    <EncryptedData Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns="http://www.w3.org/2001/04/xmlenc#">
        <EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
            <EncryptedKey xmlns="http://www.w3.org/2001/04/xmlenc#">
                <EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
                <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
              </KeyInfo>
                <CipherData>
                    <CipherValue>DeZulSs6L5Gag1b03pfp/FuynV6saKt2QYLDFuzfobQZFkMBZlWiUzKww...</CipherValue>
                </CipherData>
            </EncryptedKey>
        </KeyInfo>
        <CipherData>
            <CipherValue>VbNUeS3AXG9IDScolGAS3Q77CfIEK4K/Gezi0osh+OmIPGAiz0a8vJp9oeknyEfaW...</CipherValue>
        </CipherData>
    </EncryptedData>
</transferPayment>
```

### Explanation for the Basic XML encryption:

The whole element `paymentMessage` is replaced by its encrypted version: element `EncryptedData`. The encryption has been done with a random symmetric key that is, itself, encrypted with the public key of the given certificate.

The `EncryptedData` is made of:

1.   `EncryptionMethod` contains the method used for encryption (that is AES256 by default)
2.   `KeyInfo` contains the `EncryptedKey` which contains the information related to the [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) symmetric key that has been generated for that purpose and encrypted here with to the public key of the given certificate
3.   `CipherData` contains the encryption value of the element `paymentMessage` that we want to encrypt.

## XML encryption using Web Service Security (WSS) OASIS Standard

The _WSS OASIS Standard_ encryption is performed when `Use Web Service Security OASIS Standard` is checked and is done according to [OASIS Standard Specification](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf).

> Note that the use of WSS OASIS Standard option requires a [SOAP XML content](https://www.w3.org/TR/soap12/). If not then an error is returned.

Example: given the following `SOAP XML content`:

```
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
    <s:Header>
    </s:Header>
    <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
        <transferPayment xmlns="http://bankconnect.dk/schema/2014">
            <paymentMessage>
                <format>ISO20022</format>
                <mimeType>text/xml</mimeType>
                <compressed>0</compressed>
                <content>PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTE2Ij8+PERvY3VtZW50IHhtbG5zOnhzaT0iaHR0cDo==</content>
            </paymentMessage>
        </transferPayment>
    </s:Body>
</s:Envelope>
```

> Note that in the case of WSS OASIS Standard, if `Element to encrypt` is empty, then the action will encrypt the first child element found in the `Body`. If none, then action will return an error.

The encryption result will look like that:

```
<?xml version="1.0" encoding="utf-8"?>
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
    <s:Header>
        <wsse:Security xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" s:mustUnderstand="1" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
            <wsse:BinarySecurityToken EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" wsu:Id="X509-a450ae60-a116-4dd5-bb9f-a0987320cf43">MIICojCCAYqgAwIBAgIIIHYpe7NybIkwDQYJKoZIhvcNAQELBQAwETEPMA0GA1UEAxMGZm9vYmFyMB4XDTIyMTAyODA4NDY...</wsse:BinarySecurityToken>
            <xenc:EncryptedKey Id="EK-4fa5d278-fe3c-4acc-8a53-2b078aa86b84" xmlns:xenc="http://www.w3.org/2001/04/xmlenc#">
                <xenc:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
                <ds:KeyInfo xmlns:ds="http://www.w3.org/2000/09/xmldsig#">
                    <wsse:SecurityTokenReference wsu:Id="Id-0a9bd273-6547-4b61-a5c9-fb4f39f28407">
                        <wsse:Reference URI="#X509-a450ae60-a116-4dd5-bb9f-a0987320cf43" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3"/>
                    </wsse:SecurityTokenReference>
                </ds:KeyInfo>
                <xenc:CipherData>
                    <xenc:CipherValue>Ew8q/zFQeMClIXlePr2lJfpX0icITU/iZ1oEOAHyXEBBzPv5vMKkpTZYZ330xHx...</xenc:CipherValue>
                </xenc:CipherData>
                <xenc:ReferenceList>
                    <xenc:DataReference URI="#ED-198b6070-e1d4-4120-8c9d-c991c47204df"/>
                </xenc:ReferenceList>
            </xenc:EncryptedKey>
        </wsse:Security>
    </s:Header>
    <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
        <xenc:EncryptedData Id="ED-198b6070-e1d4-4120-8c9d-c991c47204df" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:xenc="http://www.w3.org/2001/04/xmlenc#">
            <xenc:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
            <ds:KeyInfo xmlns:ds="http://www.w3.org/2000/09/xmldsig#">
                <wsse:SecurityTokenReference d5p1:TokenType="http://docs.oasis-open.org/wss/oasis-wss-soap-message-security-1.1#EncryptedKey" xmlns:d5p1="http://docs.oasis-open.org/wss/oasis-wss-wssecurity-secext-1.1.xsd" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
                    <wsse:Reference URI="#EK-4fa5d278-fe3c-4acc-8a53-2b078aa86b84"/>
                </wsse:SecurityTokenReference>
            </ds:KeyInfo>
            <xenc:CipherData>
                <xenc:CipherValue>6znGjVGrO8TeFokTLO6qVPtQBAZBId61GkHuThAdpIiPcZ6m1b9ouQQ7xmpexArCPoFF...</xenc:CipherValue>
            </xenc:CipherData>
        </xenc:EncryptedData>
    </s:Body>
</s:Envelope>
```

### Explanation for the WSS OASIS Standard XML encryption:

1.   The element `transferPayment`, that is the first child element of the initial SOAP Body, has been replaced by its encrypted version: `xenc:EncryptedData` element

2.   A new Security element `wsse:Security` has been created in the SOAP Header. This Security element is made of:

    *   `xenc:EncryptedKey` that contains the encrypted value of the symmetric key that has been generated and used to encrypt the element to encrypt.

    *   `wsse:BinarySecurityToken` that contains the base64 encode of the public key of the given certificate and that has been used to encrypt the symmetric key above.

> **NOTE**: Unlike in _Basic Encryption_, the `EncryptedKey` element is not located in the `EncryptedData`, but in this `Security` element.
