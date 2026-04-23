# XSLT Transformation

## Description

The **XSLT Transformation** enables to transform a given input XML into an output by using an XSL Stylesheet in version 1.0.

> Note: If the stylesheet has been designed in XLST version 2 or more, the [XSLT3 Transformation](https://docs-external.u4pp.com/extensions-kit/built-in-actions/xslt3-transformation/) action should be used instead

## Usage

![Image 5: Configuring XSLT Transformation](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xslt-transformation-config.png)

An **XSLT Transformation** can be used to transform XML data from a previous step into the desired output using an XSL Stylesheet. The source XML data must be provided in the `Source XML` field. This can be a reference to the XML provided in a previous step or the XML data inline.

Additionally, an XSL Stylesheet must be provided in two different ways:

*   **Link**: select the `XSL Stylesheet Source` type to be `Link` and provide an URI to the XSL Stylesheet.

*   **Content**: select the `XSL Stylesheet Source` type to be `Content` and provide the content of the XSL Stylesheet in the XML editor provided.

Once the **Source XML** and **XSL Stylesheet Source** are defined and the action executed, the output will be inside a property called `TransformationOutput` as a string value, ready to be used in next steps.

![Image 6: XSLT Transformation output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xslt-transformation-output.png)![Image 7: XSLT Transformation reference](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xslt-transformation-output-2.png)
