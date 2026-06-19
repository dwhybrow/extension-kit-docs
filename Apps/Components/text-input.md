The **Text input** component is an input field that allows users to enter information. It can also be used to display prepopulated information to the user.

## Example

You can use the **Text input** component to create an app to modify your customer information. In this example:

-   Users can view the _Customer ID_ in the **Text input** component.
-   Users can edit the _Short name_ in the **Text input** component.

> Note: The **Text input** component follows [the WCAG 2.0 AA accessibility guidelines](https://www.w3.org/). See the [**Properties**](https://docs-external.u4pp.com/extensions-kit/app-studio/components/text-input-ripple/#properties) section for accessibility configuration tips.

![Text input component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/textinputusage2.png)

## Properties

The following **Text input** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [Templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Label_|Enter the name you want to be displayed above the component. To make the component accessible to assistive technology, make sure to be as descriptive as possible. For example, if the expected input is an email, enter a descriptive label such as 'Enter your email'.|Yes|
|_Placeholder_|Enter the text you want to display in the field before the user takes any action. By default, 'Placeholder' text is displayed. To make the component accessible to assistive technology, make sure to be as descriptive as possible. For example, if the expected input is an email, enter a descriptive placeholder such as 'example@email.com'.|No|
|_Description_|Add a description for the component. The text is displayed above the component.|No|
|_Hint_|Enter a text under the component to give the user any additional information. Validation messages have priority and will hide the hint temporarily.|No|
|_Default value_|Enter a value to appear by default.|No|

> Note: See [Templating drop-down](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/templating-dropdown/) for more details on rendering dynamic content using Liquid JS.

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Type_|Select a format from the drop-down menu.|No|
|_Size_|Select a size from the drop-down menu.|No|
|Available only for _Text, Search, Url, Phone number, Email,_ and _Password_ _Types_:|
|_Min length_|Enter the minimum number of characters allowed.|No|
|_Max length_|Enter the maximum number of characters allowed.|No|
|_Show count_|Select the checkbox to show the user the number of entered and remaining characters.|No|
|Available only for _Date, Month, Time, Datetime-local,_ and _Number_ _Types_:|
|_Min_|Enter the minimum value allowed.|No|
|_Max_|Enter the maximum value allowed.|No|

> Note: The _Align_ property in **Columns** is set to _Stretch_ by default, so the component will take all the available width. To change that, set the _Align_ property to _Left_, _Center_ or _Right_.

### Validation properties

The following table describes the validation properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Optional field_|Turn on to make the component optional. By default, the component is required.|No|
|_Add rule_|Add rules in Liquid JS to specify when the component is required. If no rules are set, the component will be required in all instances.|No|
|_Message_|Enter a message to be displayed if the user does not fill in the input. A default message is otherwise shown.|No|
|_Choose common pattern_|Select the expected input data from the drop-down. See [Available common patterns](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#available-common-patterns) for more details.|No|
|_Additional validations_|Select any or all checkboxes to add validations.|No|
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
|_Read only_|Select the checkbox to set the component to read-only.|No|
|_Add rule_|You can set rules to prevent the user form editing the component, using Liquid JS. If no rules are set, the component will be read-only in all instances.|No|

> Note: See [Add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more details on setting rules for these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Aria label_|Enter a text that allows assistive technology to attach a label to the component.|No|
|_Title_|Enter a text that is displayed as a tooltip when hovering the mouse over the component in the end-user app.|No|

## Events

The **Text input** component supports the **On update** event. See [Logic drawer](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details. ![Text input logic map](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/textinputrippleevents.png)
