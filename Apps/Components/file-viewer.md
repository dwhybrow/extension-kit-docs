The **File viewer** component allows users to preview and interact with different file types (documents and images).

## Example

You can use the **File viewer** component to allow the end-user app to preview and download their payslips.

![File viewer component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/file-viewer-2.png)

> Note: The **File viewer** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **File viewer** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Files_|Enter the resource to return the files for the component. You can choose an array from the **Templating** drop-down displayed when selecting the **Plus (+)** button (only arrays will be available) or type it in using Liquid JS. For example `{{res1}}`
Note: You must edit the Resource in the Resources tab.|Yes|
|_Name_|The name to be displayed in the toolbar. Import a value using Liquid JS from the previously imported array in _Files_. For example, `{{name}}`.|No|
|_Content_|This is the actual file (in base64 or a URL) to be displayed. Import a value using Liquid JS from the previously imported array in _Files_. For example, `{{content}}`.|No|
|_Content type_|This is the mime type of the file, for example: application/pdf or image/png. Import a value using Liquid JS from the previously imported array in _Files_. For example, `{{contentType}}`.|No|
|_Alt_|Enter a descriptive text in case the image/s cannot be displayed. If left empty, the Name property will be used. _Alt_ property only works for images.|No|
|_Responsive_|Select to maintain the original image ratio. It overrides the _Height_ property.|No|
|_Height_|Enter the height in pixels. The default value is set to 520.|Yes|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.
> 
> Note: The _Align_ property in **Columns** is set to _Stretch_ by default, so the component will take all the available width. To change that, set the _Align_ property to _Left_, _Center_ or _Right_.

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.
