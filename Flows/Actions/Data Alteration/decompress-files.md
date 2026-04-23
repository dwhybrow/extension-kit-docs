# Decompress files

The **Decompress files** action decompresses a ZIP file and produces a list of Base64 encoded files.

## Action input

![Image 4: Decompress files input](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/decompress-input.png)

The following table describes the fields in the **Decompress files** action input:

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _File_ | Select the ZIP file to decompress from the **Suggestions** drop-down. You can use Liquid. | Yes |

## Action output

![Image 5: Decompress files output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/decompress-output.png)

The following table describes the properties in the **Decompress files** action output:

| **Property** | **Description** |  |
| --- | --- | --- |
| _Files_ | An array containing the decompressed files. |  |
|  | _Name_ | The name of each decompressed file. |
|  | _Content_ | The Base64 encoded content of each decompressed file. |
