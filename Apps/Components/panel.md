The **Panel** component allows you to present content to your users in a clear and structured way by providing a stable layout.

## Example

You can use the **Panel** component to create a Register form with **Text input** and **Dropdown** components in the content section and a **Button** to submit the form in the footer.

![Panel component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/panelcomponent.png)

> Note: The **Panel** component follows the [WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Panel** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Title_|Enter the text you want as the heading.|Yes|
|_Subtitle_|Enter the text you want to display below the _Title_.|No|
|_Icon before_|Select an icon or type to search. This displays to the left of the _Title_.|No|
|_Icon after_|Select an icon or type to search. This displays to the right of the _Title_.|No|
|_Collapsible_|Turn on to make the Panel collapsible via a chevron button.|No|
|_Summary_|Enter a text to show as a summary when the Panel is collapsed. By default, no summary is shown. Available only when _Collapsible_ property is on.|No|

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Background color_|Select a background color for the container from the drop-down.|No|
|_Content size_|Select the size from the drop-down menu.|No|
|_Hide footer_|Turn on to hide the footer.|No|
|_Hide border_|Turn on to hide the border.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.
