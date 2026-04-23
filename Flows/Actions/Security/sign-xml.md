# XML Sign

## Description

The **XML Sign** action applies an [XML signature](https://csrc.nist.gov/glossary/term/xml_signature) to [XML formatted data](https://www.w3.org/standards/xml/core#summary).

## Usage

![Image 4: XML Sign basic configuration](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xml-sign-configuration.png)

This action creates an **XML Signature** that guarantees both the integrity and authenticity of the message. This allows to verify that data was not altered after it was signed with a digital certificate. The syntax of the XML signature follows the standard provided by the [W3C](https://www.w3.org/TR/xmldsig-core/).

1.   Select an available digital certificate you want to use 
2.   Choose one of the available signature structures (enveloped, enveloping or detached) 
3.   Insert the XML formatted message you want to sign (you can also insert data referring to a previous step by clicking the add [+] button)

> **NOTE** The available certificates present in the _Client certificate_ drop down menu are stored in the _Certificates_ section of Extension Kit. For more information, please see our [documentation](https://docs-external.u4pp.com/extensions-kit/guides/portal/certificates/)

### Detached Signature Elements

In the case you have selected the _Detached_ signature creation structure, you will be also prompted to select which element or elements to sign.

It is also possible to sign using the _Web Service Security OASIS Standard_ by selecting the matching option. For more information regarding this standard please check the [official documentation](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=wss).

![Image 5: Example XML Sign Detached elements to sign](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xml-sign-detached-options.gif)

> **NOTE**: You can separate the various elements to sign using a semicolon `;`

## Enveloped Signature Output Sample

> **Description**: The signature is inside the XML data that is signing

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Document xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.03">
  <CstmrCdtTrfInitn>
    <GrpHdr>
      <MsgId>ERPxAP3C</MsgId>
      <CreDtTm>2022-01-19T06:55:00</CreDtTm>
      <NbOfTxs>4</NbOfTxs>
      <CtrlSum>4433.00</CtrlSum>
      <InitgPty>
        <Nm>Dutch office supplies, office furniture and coffee machines trading co</Nm>
        <Id>
          <OrgId>
            <Othr>
              <Id>KVK9937465</Id>
            </Othr>
          </OrgId>
        </Id>
      </InitgPty>
    </GrpHdr>
  </CstmrCdtTrfInitn>
  <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
    <SignedInfo>
      <CanonicalizationMethod Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />
      <SignatureMethod Algorithm="http://www.w3.org/2001/04/xmldsig-more#rsa-sha256" />
      <Reference URI="">
        <Transforms>
          <Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature" />
          <Transform Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />
        </Transforms>
        <DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256" />
        <DigestValue>kEWCFOFB9GKq8x61Q9YR+v0WDBXO0CKcxseOjag7rSA=</DigestValue>
      </Reference>
    </SignedInfo>
    <SignatureValue>bqDDD9ObByZWWQODuciNlg+T6zsW0RxTeiTxRu5g0ZRKzIwqYTjGM11wenNTblinZqa6t++bQ8=</SignatureValue>
    <KeyInfo>
      <X509Data>
        <X509Certificate>MIIC+zCCAeOgAwIBAgIDASxVMA0GCSqGSIb3DQEBBQUAMGQxCzAJo1NzKBgQCClm8tj/+</X509Certificate>
      </X509Data>
    </KeyInfo>
  </Signature>
</Document>
```

The length of _SignatureValue_ and _X509Certificate_ data has been reduced to simplify this example

## Enveloping Signature Output Sample

> **Description**: The signed XML data is contained within an Object element within the Signature element.

```xml
<Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
  <SignedInfo>
    <CanonicalizationMethod Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />
    <SignatureMethod Algorithm="http://www.w3.org/2001/04/xmldsig-more#rsa-sha256" />
    <Reference URI="#doc">
      <DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256" />
      <DigestValue>U9UAQbjZfDVEEe67zrfJ3a5XB0XxVd5XhRgs2+ffurw=</DigestValue>
    </Reference>
  </SignedInfo>
  <SignatureValue>xkJhP6TJ9ZwJHxLLR9j4FwVVX8ITiv2xfuP4VcG6VU+CUM3QTM+cJQ==</SignatureValue>
  <Object Id="doc">
    <ApplicationRequest xmlns="http://bxd.fi/xmldata/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance/">
      <CustomerId>123456</CustomerId>
      <Command>UploadFile</Command>
      <Timestamp>2022-03-01T11:51:26.993+01:00</Timestamp>
      <Environment>PRODUCTION</Environment>
      <TargetId>5780860238</TargetId>
      <SoftwareId>WTSSWebServices</SoftwareId>
      <FileType>NDCAPXMLI</FileType>
      <Content>PD94bWwgdmVyc2lvbj0iMS4wIiBCB4bWxuczp4c2k9Imh0dHA6Ly93d3cudzMub3JnnQ+</Content>
    </ApplicationRequest>
  </Object>
</Signature>
```

The length of _SignatureValue_ and _Content_ data has been reduced to simplify this example

## Detached Signature Output Sample

> **Description**: A detached signature is neither enveloping nor enveloped. It is a type of digital signature that is kept separate from its signed data, as a sibling element.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<internally-detached>
  <ds:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">
    <ds:SignedInfo>
      <ds:CanonicalizationMethod Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315"/>
      <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#rsa-sha1"/>
      <ds:Reference URI="#data">
        <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
        <ds:DigestValue>MNMuc6DNjQ+icWWlRZGBn24qR7HIxn3Bs+CKQDI2au8=</ds:DigestValue>
      </ds:Reference>
    </ds:SignedInfo>
    <ds:SignatureValue/>
  </ds:Signature>

  <document Id="data">
     <title>title</title>
     <author>writer</author>
     <date>today</date>
     <content>
        <para>First paragraph</para>
        <para>Second paragraph</para>
     </content>
  </document>
</internally-detached>
```
