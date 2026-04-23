# Certificates

The **Certificates** page allows users with **Owner** and **Contributor** roles to manage all the certificates used in Extension Kit.

The page lists the certificates that are currently added to the tenant, and shows the following:

*   Name
*   Issuer
*   Valid from date
*   Expiration date
*   User who added the certificate

You can delete certificates using the **Delete** button. Note that this cannot be undone.

![Image 6: Certificates screen](https://docs-external.u4pp.com/extensions-kit/images/portal/certificates-screen-1.png)

## Add new certificates

To add a new certificate, click the **New certificate** button to open a modal window where you upload a certificate, either by using drag and drop or browsing for the certificate file.

The supported certificates file formats are:

*   `.cer`
*   `.pem`
*   `.pfx`
*   `.p12`

You must provide a name for the certificate. Additionally, for .pfx and .p12 certificates, you must also provide the password that matches the certificate's password.

A .pem file format can contain one or more certificates, along with a private key. Note that Extension Kit supports only `.pem` file format certificates with a single certificate.

> Note: Extension Kit does not allow .pem files with multiple certificates and/or private keys.
> 
> 
> Note: _Extension Kit Private Certificates_ are stored in Microsoft Azure Key Vaults. See the Microsoft documentation [Key types and protection methods](https://docs.microsoft.com/en-us/azure/key-vault/keys/about-keys#key-types-and-protection-methods) for the supported key length and types ("_RSA_" and "_EC_").

![Image 7: Add certificate, how to](https://docs-external.u4pp.com/extensions-kit/images/portal/certificates-screen-2.png)

## Edit certificates

You can edit certificates that are already created using the context menu in the **Certificates** table. You have the following options:

*   **Rename**: Change the certificate's name. Once changes are saved, the new name appears in the **Certificates** table and is also updated in the _Client certificate_ field in the **HTTP Request** action.

![Image 8: Rename certificate, how to](https://docs-external.u4pp.com/extensions-kit/images/portal/certificates-rename.png)

*   **Edit certificate**: Change all of the certificate's setup. You can change the _Name_ and also add a new _file_ and _password_. Changes are applied both in the **Certificates** table and in the _Client certificate_ field in the **HTTP Request** action.

![Image 9: Edit certificate, how to](https://docs-external.u4pp.com/extensions-kit/images/portal/certificates-edit.png)

> Note: The provided certificate data replaces the previous data.

It is not possible to change a certificate already created as a _public certificate_ (with a `.cer`or `.pem` extension, and therefore without an associated password) to a private one (`.pfx` or `.p12`) and vice versa.
