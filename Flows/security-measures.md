# Security measures

Extension Kit implements security measures to protect flows from malicious code execution.

## Run code action security

The **Run code** action has the following security restrictions:

### 1. Run code action file restrictions

The **Run Code** action does not allow files of any kind to be opened or executed within the action. This prevents:

*   Direct file system access
*   Execution of binary files
*   Loading of external scripts or libraries

### 2. Secure file content retrieval

File content must be received using **SFTP actions**. This ensures that file operations are authenticated, encrypted, and auditable.

### 3. Automated content scanning

All file content processed within flows is automatically scanned for potentially dangerous keywords and patterns. Content containing identified threats is rejected before execution.

### 4. Confidential security keywords

For security purposes, the list of blocked keywords is not publicly disclosed. This prevents malicious actors from identifying and circumventing security measures.

> Note: See [Run Code action](https://docs-external.u4pp.com/extensions-kit/built-in-actions/run-code/) and [Service Limits - Run Code action](https://docs-external.u4pp.com/extensions-kit/architecture/service-limits/#run-code-action) for more details.
