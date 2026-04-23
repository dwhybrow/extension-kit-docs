# SFTP - Create file

The **SFTP - Create file** action allows to create a file on an SFTP server.

You must create the SFTP server connection details beforehand on the [**SFTP Connections window**](https://docs-external.u4pp.com/extensions-kit/guides/portal/sftp-connections/) on the Extension Kit Portal.

### Action input

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Connection name_ | Choose the SFTP server connection from the drop-down. The create operation will be performed using the server details and credentials set on the connection chosen. | Yes |
| _Folder path_ | Enter, or select from the **Suggestions** drop-down, the path to the folder where you want to create the file. | Yes |
| _File name_ | Enter, or select from the **Suggestions** drop-down, a name for the new file. | Yes |
| _File content_ | Enter the file content in any text format. You can use the **Suggestion** drop-down to enter dynamic content. | Yes |

> Note: If the file already exists in the same path, an error will be returned. Overwriting is not allowed.

![Image 4: SFTP - Create Input](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/sftp-create-action.png)

### Action output

| **Property** | **Description** |
| --- | --- |
| _FileName_ | The complete path of the created file. |

![Image 5: SFTP - Create Output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/sftp-create-action-output.png)
