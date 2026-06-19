The **Radio** component allows the user to select one option from a set of mutually exclusive components.

## Example

You can use the **Radio** component to create an app that:

-   Allows the user to select a preferred date for a meeting out of a predetermined selection.
-   Triggers a flow sending them an invitation for the selected meeting.

![Radio component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/radioripple.png)

> Note: The **Radio** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/).

## Properties

The following **Radio** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Label_|Enter the text you want to display above the component.|Yes|
|_Description_|Add a description for the component. This is displayed under the _Label_.|No|
|_Hint_|Enter a text under the component to give the user any additional information. Validation messages have priority and will hide the hint temporarily.|No|
|_Options_|Enter the resource to return the data for the component, these will be the Radio options. You can choose the array from the **Templating** drop-down displayed when selecting the **Plus (+)** button (only arrays will be available) or type it in using Liquid JS. For example `{{res1}}`.
**Note:** You must edit the _Resource_ in the **Resources** tab.|No|
|_Value field_|This is the real data associated with the options. Import a value using Liquid JS from the previously imported array in _Options_. For example, `{{code}}`.|No|
|_Display field_|This is what is visible to the user. Import a value using Liquid JS from the previously imported array in _Options_. For example, `{{name}}`.|No|
|_Default value_|Enter a value from the _Value field_ if you want an _Option_ to appear selected by default.
**Note:** If the value is an integer number returned by a Resource, you must add `{}`for it to work. For example: `{{1}}`.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Validation properties

The following table describes the validation properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Optional field_|Turn on to make the component optional. By default, the component is required.|No|
|_Add rule_|Add rules in Liquid JS to specify when the component is required. If no rules are set, the component will be required in all instances. See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details.|No|
|_Message_|Enter a message to be displayed if the user does not fill in the input. A default message is otherwise shown.|No|
|_Additional validations_|Select any or all of the following checkboxes to add validations.|No|
|_Error_|Select the checkbox to add a red error style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the error validation is shown.|Yes|
|_Error message_|Enter a message to be displayed if the user fills in the input incorrectly.|Yes|
|_Warning_|Select the checkbox to add an orange warning style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the warning validation is shown.|Yes|
|_Warning message_|Enter a message to give the user advice on how to better fill in the input.|Yes|
|_Positive_|Select the checkbox to add a green positive style validation to the component.|No|
|_Add rule_|Add rules in Liquid JS to specify when the positive validation is shown.|Yes|
|_Positive message_|Enter a message to tell the user that the input has been correctly filled in.|Yes|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details.

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

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules for these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Aria label_|Enter a text that allows assistive technology to attach a label to the component.|No|
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app.|No|

## Events

The **Radio** component supports the **On update** event. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

![Radio logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/radioeventripple.png)
