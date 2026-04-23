# SFTP - List directory

The **SFTP - List directory** action lists a directory from an SFTP server.

You must create the SFTP server connection details beforehand on the [**SFTP Connections window**](https://docs-external.u4pp.com/extensions-kit/guides/portal/sftp-connections/) on the Extension Kit Portal.

### Action input

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Connection name_ | Choose the SFTP server connection from the drop-down. The list operation will be performed using the server details and credentials set on the connection chosen. | Yes |
| _Folder path_ | Enter, or select from the **Suggestions** drop-down, the path to the desired folder. | Yes |
| _List recursively_ | Select to perform the list operation on subfolders recursively. If not selected, only the first level of the _Folder path_ will be listed. | No |

![Image 4: SFTP - List Input](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/sftp-list-action2.png)

### Action output

| **Property** | **Description** |  |
| --- | --- | --- |
| _Files_ | A collection of files or folders from the SFTP server. Each entry contains the following properties: |  |
|  | _Name_ | The name of the file/folder. |
|  | _Path_ | The full path to the file/folder. |
|  | _MediaType_ | The content type inferred from the file extension. Empty for folders. |
|  | _LastModified_ | The last time the file/folder was modified. |
|  | _Size_ | The file size in bytes. Zero for folders. |
|  | _IsFolder_ | Whether the entry is a file or a folder. |

![Image 5: SFTP - List Output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/sftp-list-action-output.png)
