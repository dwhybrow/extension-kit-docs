The **Checkbox** component gives users a binary choice (select/clear).

## Example

You can use the **Checkbox** component to make sure the user agrees to continue with a process. In this example, the button becomes active when the user agrees to terms and conditions.

![Checkbox component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/checkboxripplecomponent.png)

> Note: The **Checkbox** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Checkbox** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Label_|Enter the text you want to appear next to the checkbox.|Yes|
|_Default value_|Enter a Boolean value (true/false) to select/clear the component by default. You can use templating or write a string, for example, the string "true" will show a selected component.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
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

The **Checkbox** component supports the **On update** event. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

![Checkbox logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/checkboxeventripple.png)
