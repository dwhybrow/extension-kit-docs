The **Combobox** component allows users to choose one option from a predefined set of choices. It also allows the user to filter through the options by typing in the input.

## Example

You can use the **Combobox** component to show the user a list of countries from which to choose. The user can:

1.  Open the options list using the chevron icon.
2.  Type to filter through the options.

![Combobox component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/comboboxcomponent.png)

> Note: The **Combobox** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Combobox** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Label_|Enter the text you want to display above the component.|Yes|
|_Placeholder_|Enter the text you want to display in the field before any option is selected. By default, 'Type to filter...' text is displayed.|No|
|_Description_|Add a description for the component. This is displayed under the label.|No|
|_Hint_|Enter a text under the component to give the user any additional information. Validation messages have priority and will hide the hint temporarily.|No|
|_Options_|Enter the resource to return the data for the component, these will be the Combobox options. You can choose the array from the **Templating** drop-down displayed when selecting the **Plus (+)** button (only arrays will be available) or type it in using Liquid JS. For example `{{res1}}`
**Note:** You must edit the _Resource_ in the **Resources** tab.|No|
|_Value field_|This is the real data associated with the options. Import a value using Liquid JS from the previously imported array in _Options_. For example, `{{code}}`.|No|
|_Display field_|This is what is visible to the user. Import a value using Liquid JS from the previously imported array in _Options_. For example, `{{name}}`.|No|
|_Default value_|Enter a value from the _Value field_. This value will be automatically selected when the user opens the app. The _Placeholder_ text displays when the user clears the selection.
**Note:** If the value is an integer number returned by a Resource, you must add `{{}}`for it to work.For example: `{{1}}`.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Size_|Select the size from the drop-down menu.|Yes|

> Note: The _Align_ property in **Columns** is set to _Stretch_ by default, so the component will take all the available width. To change that, set the _Align_ property to _Left_, _Center_ or _Right_.

### Validation properties

The following table describes the validation properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Optional field_|Turn on to make the component optional. By default, the component is required.|No|
|_Add rule_|Add rules in Liquid JS to specify when the component is required. If no rules are set, the component will be required in all instances. See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details.|No|
|_Message_|Enter a message to be displayed if the user does not fill in the input. A default message is otherwise shown.|No|

To perform validation before submitting data you must use the **Field validation** action in the **Logic drawer**. See relevant documentation for more details:

-   [Field validation action](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#field-validations-action).
-   [Validation](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/) and the [Example: Validating date input before sending data](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#example-validating-date-input-before-sending-data) section for step-by-step guidance.

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

## Events

The **Combobox** component supports the **On update** event. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.
