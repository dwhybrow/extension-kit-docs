# Actions overview

An action is a component that is executed as part of a running flow.

Actions can accept an optional input from the flow and return the result of the execution (succeeded or failed), along with an optional output, back to the flow.

Every action is responsible for defining the format of its input and output, both of which can be complex objects, the only requirement is that they can be serialized to JSON.

See [action definition](https://docs-external.u4pp.com/extensions-kit/glossary/action/) for more details.

## Available actions

### Communication

**Communication** actions can send or retrieve data from other actors.

| Action | Description |
| --- | --- |
| **Email sender** | Send an email message. |
| **Event grid publish** | Send an event to an Event grid topic. |
| **HTTP request** | Make an HTTP request to the specified URL. |
| **SFTP - Create file** | Create a file in an SFTP server. |
| **SFTP - Delete file** | Delete a file in an SFTP server. |
| **SFTP - Get file content** | Retrieve a file content from an SFTP server. |
| **SFTP - List directory** | List all files from an SFTP server directory. |

### Control

**Control** actions can manipulate the sequence of the flow.

| Action | Description |
| --- | --- |
| **Execute templating script** | Execute a templating script using Liquid language. |
| **For each** | Iterate over a set of items. |
| **Pause** | Pause the execution of a flow. |
| **Stop** | Stop the execution of the flow. |
| **Until** | Execute a block of actions until a specified condition evaluates to true. |

### Data alteration

**Data alteration** actions can transform the original format of the data.

| Action | Description |
| --- | --- |
| **Compress files** | Compress one or several files into a ZIP. |
| **Decompress files** | Decompress a given file. |
| **JSON parse** | Parse a JSON content to a specific schema. |
| **JSON to XML** | Transform JSON to XML. |
| **XML parse** | Transform XML to JSON. |
| **XSLT transformation** | Transform an XML using an XSLT 1.0 Stylesheet. |
| **XSLT3 transformation** | Transform an XML using an XSLT 3.0 Stylesheet. |
| **File flat to JSON** | Transform a flat file to JSON. |
| **Run code** | Execute JavaScript code. |
| **Run code using Forge library** | Execute a block of actions until a specified condition evaluates to true. |

### Security

**Security** actions can add security measures to the data transaction, like encryption, decryption and authentication.

| Action | Description |
| --- | --- |
| **Generate JWT token** | Create a JWT token. |
| **PGP encrypt** | Encrypt a file using Pretty Good Privacy (PGP) standard. Encrypt a file using Pretty Good Privacy (PGP) standard. |
| **PGP decrypt** | Decrypt a file using Pretty Good Privacy (PGP) standard. |
| **XML encrypt** | Encrypt an XML file either partially or fully using a certificate. |
| **XML decrypt** | Decrypt an XML file using a certificate. |
| **XML sign** | Sign an XML file using a certificate. |
| **XML verify** | Verify the signature of an XML file. |

### Unit4 Ecosystem

**Unit4 ecosystem** actions can communicate with and retrieve data from other Unit4 products.

| Action | Description |
| --- | --- |
| **Unit4 Ava push text** | Send a message to a user using Unit4 Ava. |
| **Unit4 Ava question** | Send a question to a user using Unit4 Ava. |
| **Message Hub actor** | Call a Message Hub actor and wait for their response. |
| **Message Hub event** | Send a message to a Message Hub receiver. |
| **Unit4Id resolver** | Retrieve the Unit4Id from a given email. |
| **App result** | Send the result of a flow to an App Studio app. |

## Action errors

When an action cannot be performed, the flow run will be unsuccessful. Go to the [**Flow history**](https://docs-external.u4pp.com/extensions-kit/guides/portal/flow-history/) for details on the error.

![Image 3: Action error](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/action-error.png)
