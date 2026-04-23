# SFTP - Delete file

The **SFTP - Delete file** action allows to delete a file from an SFTP server.

You must create the SFTP server connection details beforehand on the [**SFTP Connections window**](https://docs-external.u4pp.com/extensions-kit/guides/portal/sftp-connections/) on the Extension Kit Portal.

### Action input

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Connection name_ | Choose the SFTP server connection from the drop-down. The delete operation will be performed using the server details and credentials set on the connection chosen. | Yes |
| _File path_ | Enter, or select from the **Suggestions** drop-down, the path to the desired file. | Yes |

> Note: This action only deletes files. Folder deletion is not supported.

![Image 4: SFTP - Delete Input](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/sftp-delete-action.png)

### Action output

| **Property** | **Description** |
| --- | --- |
| _Message_ | The description of the result of the operation. |

![Image 5: SFTP - Delete Output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/sftp-delete-action-output.png)
