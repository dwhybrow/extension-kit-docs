The **Link** component allows users to navigate to another place in the page, another page or another page in a new tab or window.

## Example

You can use the **Link** component to redirect the user to an external site, for example a satisfaction survey.

![Link component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/linkcomponent.png)

> Note: The **Link** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Link** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Label_|Enter the text you want to show the user.|No|
|_Url_|Enter the link you want the user to follow. You can use templating.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Target_|Select the target to specify where to open the new page.|No|
|_Size_|Select the size.|No|
|_Variant_|Select the appearance.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app. For icons that convey meaning (semantic icons) enter a descriptive title for screen readers. No title is needed for decorative icons.|No|
