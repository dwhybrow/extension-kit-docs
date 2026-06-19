The **Switch** component allows users to choose between two mutually exclusive options.

## Example

You can use the **Switch** component to customise further the user experience allowing them to enable certain app features. In this app:

-   Users can choose whether to see the dinner menu options or not.

![Switch component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/switchripplecomponent.png)

> Note: The **Switch** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Switch** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Label_|Enter the text you want to display next to the component.|Yes|
|_Default value_|Enter a Boolean value (true/false) to turn on/off the component by default. You can use templating or write a string, for example, the string "true" will turn on the component.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Size_|Select the size from the drop-down menu.|No|
|_Label position_|Select the _Label_ position from the drop-down menu.|No|

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the Eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|
|_Disabled_|Select the checkbox to disable the component in the end-user app.|No|
|_Add rule_|You can set rules to disable the component using Liquid JS. If no rules are set, the component will be disabled in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app.|No|

## Events

The **Switch** component supports the **On update** event. See [Events and actions](https://docs-external.u4pp.com/extensions-kit/app-studio/components/logic/events-actions-ripple-nowlogicdrawer.md#actions) for more details.

![Switch logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/switcheventripple.png)
