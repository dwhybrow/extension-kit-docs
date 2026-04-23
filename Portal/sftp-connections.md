# SFTP Connections

The **SFTP Connections** window allows you to configure and manage the SFTP connections used in the available **SFTP** actions.

SFTP connections support the [SSH.NET library version 2024.1.0](https://github.com/sshnet/SSH.NET/releases/tag/2024.1.0).

> Note: Only users with **Owner** and **Contributor** roles can manage SFTP connections.

![Image 5: SFTP Connections window](https://docs-external.u4pp.com/extensions-kit/images/portal/sftp-connection-window.png)

The window shows the:

1.   Main toolbar: [Basic search](https://docs-external.u4pp.com/extensions-kit/guides/portal/sftp-connections/#basic-search)
2.   [SFTP connections list](https://docs-external.u4pp.com/extensions-kit/guides/portal/sftp-connections/#sftp-connections-list)
3.   Bottom toolbar: [**New connection** button](https://docs-external.u4pp.com/extensions-kit/guides/portal/sftp-connections/#new-connection-button)

## 1. Main toolbar

### Basic search filter

Select the **Lens icon** button to search for the SFTP connection by _Connection name_.

## 2. SFTP connections list

It shows the SFTP connections that are currently added to the tenant. It displays the following data:

| **Column** | **Description** |
| --- | --- |
| _Connection name_ | A user-defined label for the SFTP connection. |
| _Host server address_ | The hostname of the SFTP server. |
| _Port number_ | The network port used for the SFTP connection. |
| _User name_ | The username for authenticating to the SFTP server. |
| _Trash can icon_ | The button to delete the SFTP connection. After selecting the button, a dialog appears to ask for confirmation. |

> Note: All values must be manually entered by the user when creating a new SFTP connection.

## 3. Bottom toolbar

### New connection button

To add a new SFTP connection:

1.   Select the **New connection** button.
2.   Enter the SFTP connection details:

![Image 6: SFTP add connection window](https://docs-external.u4pp.com/extensions-kit/images/portal/sftp-new-connection7.png)

| **Field** | **Description** |  |  |
| --- | --- | --- | --- |
| _Name_ | Enter a descriptive name for your connection. |  |  |
| _Host_ | Enter the hostname of the SFTP server. It is provided by the server administrator or the relevant documentation. |  |  |
| _Port_ | Enter the network port used for the SFTP connection. The default SFTP port is 22, but it might vary depending on the server configuration. |  |  |
| _User_ | Enter the username for authenticating to the SFTP server. This is assigned by the server administrator and must be known in advance. |  |  |
| _Authentication type_ | Select the desired radio button, and fill in the fields: |  |  |
|  | _Password_ | _Password_ | Enter the password associated to the _User_. |
|  |  | _SSH hostkey fingerprint_ | Enter the SSH key of the server to verify its identity. |
|  | _SSH private key_ | _SSH private key_ | Enter the full contents of the private key file. |
|  |  | _SSH private key passphrase_ | For added security, enter the key passphrase if the matching key requires one. |
|  |  | _SSH hostkey fingerprint_ | Enter the SSH key of the server to verify the its identity. |
|  | _Dual_ | _Password_ | Enter the password associated to the _User_. |
|  |  | _SSH hostkey fingerprint_ | Enter the SSH key of the server to verify the its identity. |
|  |  | _SSH private key passphrase_ | For added security, enter the key passphrase if the matching key requires one. |

> Note: The _Dual_ authentication type is an early version only available in non-production environments. See [early version](https://docs-external.u4pp.com/extensions-kit/glossary/early-version/) for more details.

#### SSH private key authentication

Only **OpenSSH formatted keys** are allowed. Also make sure that the _private key_ is properly formatted. Missing characters and/or incorrect formatting will result in an error.

![Image 7: SFTP SSH Private Key Authentication](https://docs-external.u4pp.com/extensions-kit/images/portal/sftp-ssh-private-key2.png)

The length of the _SSH private key_ data has been reduced to simplify this example.
