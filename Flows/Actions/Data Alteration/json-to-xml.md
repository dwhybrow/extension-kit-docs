# JSON to XML

## Description

**JSON to XML** enables to convert a given JSON input into an XML output.

## Usage

![Image 9: Configuring JSON to XML](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-to-xml-config-content-from-body.png)

**JSON to XML** can be used to convert JSON data from a previous step into an XML output. The source JSON data must be provided in the `JSON Content` field. This can be a reference to the JSON provided in a previous step, as shown above, or the JSON data inline, as shown below.

![Image 10: Json To Xml Config Content From Body](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-to-xml-config-content.png)

Additionally, a JSON source must be provided in two different ways:

*   Content: select the `JSON source` type to be `Content` and provide the JSON content in the JSON editor provided, as shown above.
*   Link: select the `JSON source` type to be `Link` and provide an URL to the JSON source URL, as shown below.

![Image 11: Json To Xml Config Link](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-to-xml-config-link.png)

Once the **JSON source** and **JSON content** or **JSON source URL** are defined and the action executed, the output will be inside a property called `XmlContent` as a string value, ready to be used in next steps.

![Image 12: JSON to XML output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-to-xml-output-jedi.png)![Image 13: JSON to XML reference](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-to-xml-output-used.png)

> **NOTE** When the JSON source string is an **array**, that is, preceded by no property, the output XML uses `ArrayList` tag to wrap the array and for each element, it uses the `Item` tag, as shown below.

![Image 14: JSON to XML output based on a JSON array](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-to-xml-output-array.png)

> **NOTE** When the JSON source string is an **object**, the output XML uses the `Root` tag to wrap the entire XML string.

![Image 15: Json To Xml Output Object](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-to-xml-output-object.png)
