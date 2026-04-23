# XSLT3 Transformation

## Description

The **XSLT3 Transformation** enables to transform a given input XML into an output by using an XSL Stylesheet version 3.0.

This action is very similar to the [XSLT Transformation](https://docs-external.u4pp.com/extensions-kit/built-in-actions/xslt-transformation/) except that it accepts stylesheet in version 3.0 and also stylesheet parameters.

> **NOTE**: More details [about XSLT3 enhancements here.](https://www.w3.org/TR/xslt-30/#whats-new-in-xslt3)

## Usage

![Image 5: Xslt3 Transformation Config](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xslt3-transformation-config.png)

An **XSLT3 Transformation** can be used to transform XML data from a previous step into the desired output using an XSL Stylesheet. The source XML data must be provided in the `Source XML` field. This can be a reference to the XML provided in a previous step or the XML data inline.

**Stylesheet Parameters** can also be provided. In the example above, the XSL parameter `test_parameter` has been defined at line 5 and it's value is provided in the Stylesheet Parameters section. This value will be used during the XSL transform process.

> **NOTE**: Templating are not allowed in the XSLT3 Stylesheet (this is the reason why the [+] button is missing from the Stylesheet textbox) but Stylesheet Parameters can be used as a workaround, as in the screenshot above with the `param_version` parameter

Once the **Stylesheet**, **Source XML** and the possible **Stylesheet Parameters** are defined and the action executed, the output will be inside a property called `TransformationOutput` as a string value, ready to be used in next steps.

![Image 6: XSLT3 Transformation Output](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xslt3-transformation-output.png)![Image 7: XSLT3 Transformation reference](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xslt-transformation-output-2.png)

> **NOTE**: There are a few minor incompatibilities between XSLT 3.0 and XSLT 2.0. For additional information, please check the [W3C documentation for all known cases](https://www.w3.org/TR/xslt-30/#incompatibilities)
