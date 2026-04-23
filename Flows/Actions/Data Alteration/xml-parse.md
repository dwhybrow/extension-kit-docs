# XML Parse

## Description

**XML Parse** enables to select and use in the templating system data from an XML output from a previous step, based on the JSON Schema provided.

## Usage

![Image 4: Configuring XML Parse](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xml-parse-form.png)

**XML Parse** can be used to reference data from XML content from a previous step by using an XML data source and a JSON Schema that represents it.

The source XML data that will be used must be indicated in the field **Source XML**. This will be a reference to a previous step field that contains an XML.

A JSON Schema that matches the XML structure must be provided to validate the data and to be used in the next steps. Using the field **Schema source**, you can define the JSON Schema to be used in two ways: from an existing one through a URL (**Link** option) or directly create it in a JSON Schema editor (**Content** option). What is defined in the JSON Schema is what will be available to pick and use in the next steps.

Once the **Source XML** and **Schema source** are defined, you can start referencing the XML Parse step in any other subsequent step:

![Image 5: Using XML Parse output in other step](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/xml-parse-usage.png)

> **NOTE** Currently we only support the draft 4 version of the [Json Schema](http://json-schema.org/)
