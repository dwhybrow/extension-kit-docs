# SFTP - Get file content

The **SFTP - Get file content** action allows to read the content of a file from an SFTP server.

You must create the SFTP server connection details beforehand on the [**SFTP Connections window**](https://docs-external.u4pp.com/extensions-kit/guides/portal/sftp-connections/) on the Extension Kit Portal.

### Action input

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Connection name_ | Choose the SFTP server connection from the drop-down. The get file content operation will be performed using the server details and credentials set on the connection chosen. | Yes |
| _File path_ | Enter, or select from the **Suggestions** drop-down, the path to the desired file. | Yes |
| _Infer content type_ | Select to infer the content type from the file extension. If not selected, the file content will be returned encoded as base64 independent of the file extension. If selected, the file content is returned as text for the following content types: text/plain text/html text/xml text/csv application/xml application/json | No |

![Image 4: SFTP - Get Content Input](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/sftp-get-action.png)

### Action output

| **Property** | **Description** |
| --- | --- |
| _ContentType_ | File media type. If not inferred or unknown, it is defaulted to `application/octet-stream`. |
| _FileContent_ | The content of the file as text or base64, depending on the configuration of the _Infer content type_ field and the content type of the file. |

![Image 5: SFTP - Get Content Output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/sftp-get-action-output.png)
