The **Range** component allows users to choose a value between a set of values.

## Example

You can use the **Range** component to allow the user to express their opinion on a feedback questionnaire:

![Range component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/semanticrange.png)

or to select a price limit:

![Range component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/numericalrange.png)

> Note: The **Range** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Range** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Label_|Enter the text you want to display above the component.|Yes|
|_Description_|Add a description for the component. This is displayed under the _Label_.|No|
|_Hint_|Enter a text under the component to give the user any additional information. Validation messages have priority and will hide the hint temporarily.|No|
|_Min. range value_|Enter a number to be the minimum range value. The default value is set to 0.|Yes|
|_Max. range value_|Enter a number to be the maximum range value. The default value is set to 100.|Yes|
|_Step size_|Enter a number to specify the increment in value from one step to another. The default value is set to 5.|Yes|
|_Default value_|Enter a number to be shown as the range default value. The handle displays in that position by default in the end-user app.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Display value_|Select the preferred option from the drop-down to configure the visibility of the Range value on top of the handle.|No|
|_Markers_|Select the preferred option from the drop-down to configure the visibility of the steps markers. This property displays the lines under the steps.|No|
|_Marker values_|Select the preferred option from the drop-down to configure the visibility of the numeric value of each marker.|No|
|_Indicators_|Turn on to display the indicators corresponding to the steps in the range track.|No|
|_Stops_|Enter an array for custom Range stops. You can use templating. It overrides _Step size_ property. To use strings in your Range create an array following this format `[[0,"Disagree"],[50,"Not relevant"],[100,"Agree"]]`.|No|
|_Units_|Append a unit to the _Marker value_ property.|No|
|_Negative_|Turn on to invert the colour coding in the range track. This property affects only the appearance of the component.|No|

> Note: The _Align_ property in **Columns** is set to _Stretch_ by default, so the component will take all the available width. To change that, set the _Align_ property to _Left_, _Center_ or _Right_.

### Interactions properties

The following table describes the interactions properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Hidden_|Select the checkbox to hide the component in the end-user app. To hide it in the canvas, use the eye icon in the _Layers_ panel.|No|
|_Add rule_|You can set rules to hide the component using Liquid JS. If no rules are set, the component will be hidden in all instances.|No|
|_Disabled_|Select the checkbox to disable the component in the end-user app.|No|
|_Add rule_|You can set rules to disable the component using Liquid JS. If no rules are set, the component will be disabled in all instances.|No|
|_Read only_|Select the checkbox to set the component to read-only.|No|
|_Add rule_|You can set rules to prevent the user form editing the component using Liquid JS. If no rules are set, the component will be read-only in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Aria label_|Enter a text that allows assistive technology to attach a label to the component.|No|
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app.|No|
