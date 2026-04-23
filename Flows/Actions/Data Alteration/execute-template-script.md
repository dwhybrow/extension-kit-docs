# Execute Templating Script

## Description

The **Execute Templating Script** action allows you to execute a Liquid script. See [Templating](https://docs-external.u4pp.com/extensions-kit/guides/portal/templating/) for more details.

## Usage

This action is used to make scripting easier and cleaner removing the need to have additional scripting logic mixed with data inside actions.

An example of a script is shown below:

![Image 5: Execute Templating](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/execute-templating-01.png)

Then these variables can be used in subsequent actions, for example, an HTTP Request action:

![Image 6: Execute Templating](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/execute-templating-02.png)

Additionally, the output of this action is the rendered template which is useful for debugging purposes as you can print values in the resulting template.

![Image 7: Execute Templating](https://docs-external.u4pp.com/extensions-kit/images/built-in-actions/execute-templating-03.png)
