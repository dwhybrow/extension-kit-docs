The **Drawing area** component allows users to draw freehand within an app and attach that drawing to the app storing the result as a base64-encoded image.

## Example

You can use the **Drawing area** component to create an app with a drawing area at the end of a form. In this app:

-   Users can fill in the different inputs.
-   Users can attach a drawing.

![Drawing area component](https://docs-external.u4pp.com/extensions-kit/app-studio/images/ripple/drawing-area-component-ripple2.png)

## Properties

The following **Drawing area** component properties are available:

### Main properties

The following table describes the main properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Component ID_|Enter a unique name for the component. See [templating in components](https://docs-external.u4pp.com/extensions-kit/app-studio/components/components-overview-ripple/#templating-in-components) for more details.|Yes|
|_Label_|Enter the name you want to be displayed above the component.|Yes|
|_Button text_|Enter the name you want to be displayed inside the button. When the user selects the button, it will clear the drawing area.|Yes|

### Styles properties

The following table describes the styles properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Size_|Select the size from the drop-down menu.|No|

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
|_Disabled rule_|You can set rules to disable the component using Liquid JS. If no rules are set, the component will be disabled in all instances.|No|

> Note: See [add rules to trigger properties](https://docs-external.u4pp.com/extensions-kit/app-studio/templating-and-liquid/liquid-support/#add-rules-to-trigger-properties) for more information on setting rules to these properties.

### Accessibility properties

The following table describes the accessibility properties of the component.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Aria label_|Enter a text designed to help assistive technology attach a label to the component.|No|
