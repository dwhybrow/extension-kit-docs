The **Text** component allows App Studio users to enter any text in their app and end-users of the app to see the displayed text.

## Example

You can use the **Text** component to create headings and subheadings in your app:

1.  Heading with templating
2.  Body text
3.  Subheading

![Text component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/textcomponent2.png)

> Note: The **Text** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Text** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Text_|Enter the text you want to display. You can use templating.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Variant_|Select the appearance from the drop-down menu.|No|
|_Font size_|Select the font size from the drop-down menu.|No|
|_Font weight_|Select the font weight from the drop-down menu.|No|
|_Text align_|Select the text alignment to the canvas from the drop-down menu.|No|
|_Color_|Select the colour according to the text function from the drop-down menu.|No|

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
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app.|No|
