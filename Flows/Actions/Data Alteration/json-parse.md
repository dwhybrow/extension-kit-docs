# JSON Parse

## Description

The **JSON Parse** action processes incoming JSON data by parsing it and interpreting it according to a defined schema. This structuring allows the data to be easily processed and manipulated by subsequent actions in the flow.

During the execution of a flow, unstructured JSON data can be received from triggers and actions, for example, from the output of a **[Webhook](https://docs-external.u4pp.com/extensions-kit/built-in-triggers/http-webhook-v2/)** trigger, or from the request body content of the output of an **[HTTP Request](https://docs-external.u4pp.com/extensions-kit/built-in-actions/http-request/)** action. This data, or part of it, can be provided to subsequent steps in the flow. Without parsing and structuring, creating the correct data referencing templates for use in later actions can be more difficult.

## Usage

You define the JSON schema to be used in the _Schema source_ field. You have the following options:

*   **Content**: You can manually enter the schema, or automatically generate it based on example JSON data using the **Generate by JSON** button.
*   **Link**: You enter the _Schema URI_ pointing to where the required schema can be read.

> Note: Currently the draft 4 version of the [JSON Schema](http://json-schema.org/) is supported.

You must also specify the content source in the _Source JSON_ field, which should be the output, or a property of the output, from a trigger or action previously defined in the flow.

![Image 4: JSON Parse Usage](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-parsev2-01.png)

When this is done, the flow designer is then able to interpret and structure the data to provide more details, and to allow you to reference specific parts of the data, for example:

![Image 5: Structured data](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/json-parsev2-02.png)
