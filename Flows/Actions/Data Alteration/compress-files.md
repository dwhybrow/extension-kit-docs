# Compress Files

## Description

The **Compress Files** action compresses a number of input files into a .zip file using the Deflate algorithm.

## Usage

### Input

Input to the action is provided as a JSON string representing a list of files, each with _Name_ and _Content_ fields representing the name and content of the file in Base64. Input is provided as JSON:

*   Provided through a Liquid object if looped with JSON parse over a directory of files, so that all files in an SFTP directory are compressed automatically. 
*   A hand coded JSON with the names and contents of the files, using this structure:

```json
[
 {
   "Name": "file1.txt",
   "Content":"base64File1Content"
 },
 {
   "Name": "file2.xml",
   "Content":"base64File2Content}"
 }
]
```

### Limits

The following limits apply:

*   The maximum stable file size for compression is 40MB - time approximately 10 seconds.
*   The maximum number of files to compress is 50.

## Examples

An example flow using a hand coded JSON file is shown below where specific files to be compressed are first retrieved from a directory and then compressed.

![Image 6: Compress files example 1](https://docs-external.u4pp.com/images/built-in-actions/compress-files-ex1.png)

An example flow is shown below using a Liquid object, where a JSON parse action is looped over an SFTP directory of files, so that all files in the directory are compressed automatically.

![Image 7: Compress files example execute templating](https://docs-external.u4pp.com/images/built-in-actions/compress-files-ex2a.png)

![Image 8: Compress files example JSON parse](https://docs-external.u4pp.com/images/built-in-actions/compress-files-ex2b.png)

![Image 9: Compress files example compress](https://docs-external.u4pp.com/images/built-in-actions/compress-files-ex2c.png)
