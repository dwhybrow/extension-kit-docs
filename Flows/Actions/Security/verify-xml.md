# XML Verify

## Description

The **XML Verify** action verifies a given XML file integrity and authenticity with a _Client Certificate_.

## Usage

![Image 3: XML Verify basic configuration](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xml-verify-configuration.png)

The **XML Verify** action checks that the _XML content_ is correctly signed with the provided _Client Certificate_ and retrives the original XML file without its [signature](https://docs-external.u4pp.com/extensions-kit/built-in-actions/sign-xml/).

1.   Select a _Client certificate_
2.   Insert the _XML content_ you want to verify for integrity and authenticity (you can also insert data referring to a previous step by clicking the add [+] button)

> **NOTE** The available certificates present in the _Client certificate_ drop down menu are stored in the _Certificates_ section of Extension Kit. For more information, please see our [documentation](https://docs-external.u4pp.com/extensions-kit/guides/portal/certificates/).
> 
> 
> **NOTE**: The XML Verify action automatically detects the type of signature structure used in the the selected XML file (enveloped, enveloping or detached).
