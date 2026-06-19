To define the logic of your app you must define the actions and events you want the app to perform when the user launches the app or when they interact with certain components.

**Event** nodes have one output port that must be connected to one or more actions. **Action** nodes can have zero, one or two output ports. See [actions](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#actions) for more details.

You can also connect events output ports and actions input and output ports to the **If** logic control. See [logic control](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#logic-control) for more details.

Events and action's logic must be configured in the **Logic drawer** that displays to the left of the window in:

## Events

The following table describes the available events:

|**Event**|**Tab**|**Description**|**Actions**|**Components**|
|---|---|---|---|---|
|_On launch_|Logic flow|Defines what happens when your app is launched.|Change screen, Dialog, Field Validation, HTTP request, Reset, Toast, Trigger flow.|
|_On finish_|Logic map|Defines what happens when the user selects the **Finish** button in the last step of the **Panel with stepper** component.|Dialog, HTTP request, Reset, Toast, Trigger Flow.|Panel with stepper|
|_On click_|Logic map|Defines what happens when the component is clicked.|Change screen, Dialog, Field Validation, HTTP request, Reset, Toast, Trigger flow.|Button|
|_On click - Item_|Logic map|Defines what happens when the items of the component are clicked.|Change screen, Dialog, Field Validation, HTTP request, Reset, Toast, Trigger flow.|Stacked list (**System apps** only)|
|_On update_|Logic map|Defines what happens when the user edits the component and tabs out of it. If the user does not change the value and/or does not tab out of it, the event does not trigger.|Dialog, HTTP request, Toast, Trigger flow|Checkbox, Combobox, Dropdown, File uploader, Radio, Switch and Text input.|

## Actions

The following table describes the available actions:

|**Action**|**Events**|**Components**|
|---|---|---|
|[HTTP Request](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#http-request)|On launch, On click, On click - Item, On update and On finish|Button, Checkbox, Combobox, Dropdown, File uploader, Panel with stepper, Radio, Switch, and Text input.|
|[Trigger flow](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#trigger-flow)|On launch, On click, On click - Item, On update and On finish|Button, Checkbox, Combobox, Dropdown, File uploader, Panel with stepper, Radio, Switch and Text input.|
|[Reset](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#reset)|On launch, On click, On click - Item and On Finish|Button and Panel with stepper.|
|[Field validation](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#field-validation)|On launch, On click and On click - Item|Button|
|[Toast](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#toast)|On launch, On click, On click - Item, On update and On finish|Button, Checkbox, Combobox, Dropdown, File uploader, Panel with stepper, Radio, Switch and Text input.|
|[Dialog](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#dialog)|On launch, On click, On click - Item, On update and On finish|Button, Checkbox, Combobox, Dropdown, File uploader, Panel with stepper, Radio, Switch and Text input.|
|[Change screen](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#change-screen)|On launch, On click and On click - Item|Button|

> Note: _On click - Item_ is only available for the **Stacked list** component in **System apps**.

### HTTP Request

The **HTTP Request** action links a REST API operation (GET, POST, PUT, PATCH, DELETE) that is defined in the [**Resources**](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/) section to the selected event.

HTTP Request nodes have one input port and two output ports: - _Green check_ handle for success output - _Red cross_ handle for error output.

> Note: GET requests linked to an event are triggered only when the event occurs.

The following table describes the **HTTP Request** action available properties:

|**Property**|**Description**|**Required**|
|---|---|---|
|_Description_|Enter an optional description of your action.|No|
|_HTTP_|Select one of all the available HTTP resources defined in the **Resources** section.|Yes|
|_Set app as saved_|Turn on to consider the user changes saved if the action is successful. When the user tries to close the end-user app without performing this action, an Unsaved changes warning appears to inform the user that changes will not be saved if they close the app. The warning does not appear if they have performed this action after making the changes. If the switch is off in all instances of the action, the message never appears.
Note: Only available for POST, DELETE, PUT and PATCH resources.|No|
|_Unlock screen while loading_|Turn on to allow the user to continue to use the app while the API calls are being made in the background. A spinner will appear to let the user know that something is happening in the background. By default, the loading spinner blocks the screen during data loading.|No|
|_Download file_|Turn on to allow a file to be downloaded to the user's local device. Only available when the **HTTP** resource has _Response type: File_.
Note: You do not need to turn on the switch to use the retrieved file for another purpose. See [**How to use a downloaded file in an API request**](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#How-to-use-a-downloaded-file-in-an-API-request) for more details.|No|
|_File content_|Select the file using the **Plus (+)** button or enter its path between `{}`. Only available when using the **ERPx/CR API** resource or the **HTTP** resource _Response type: JSON_.
Note: R&D Unit4 developers can also use the **Unit4 service** resource.|No|
|_File name_|Enter the name for the downloaded file. If the API does not provide a file name in the `Content-Disposition` header, and the _File name_ property is empty, the file will be named _download_.|No|

In the example below we can see how to upload multiple data sets. Three **HTTP Request** actions are linked to the **On launch** event to load _Customers_, _Countries_, and _Customer groups_ when the app starts. Three resources are created in the **Resources** section with the necessary REST API operations defined.

![HTTP Request on launch example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/httplogicflow3.png)

In the example below we can see how to upload a file. An **HTTP Request** action is linked to the **On click** event for a **Button** component. When the button is selected, the HTTP request is triggered for a `POST` operation to upload a document. There is one resource created in the **Resource** section with the necessary REST API operations defined.

![HTTP Request upload example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/httplogicmap3.png)

In the example below we can see how to allow the user to download a file. An **HTTP Request** action is linked to the **On click** event for a **Button** component. When the button is selected, the file is downloaded. The _Download file_ is enabled and _File name_ is empty so when the request is successful, the file is downloaded with 'download' as a name. There is one resource created in the **Resource** section with the necessary REST API operations defined.

![HTTP Request download file example](https://docs-external.u4pp.com/extensions-kit/app-studio/images/httplogicmap6.png)

### Trigger flow

The **Trigger flow** action allows you to trigger an **Extension Kit** flow at a certain point in the app's logic. See [Flow resource](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#flow) for more details.

The following table describes the **Trigger flow** action available properties:

|**Property**|**Description**|**Required**|
|---|---|---|
|_Description_|Enter an optional description of your action.|No|
|_Flow_|Select the configured flow to use. See [Flow resource](https://docs-external.u4pp.com/extensions-kit/app-studio/resources/#flow) for more details.|Yes|
|_Set app as saved_|Turn on to consider the user changes saved if the action is successful. When the user tries to close the end-user app without performing this action, an Unsaved changes warning appears to inform the user that changes will not be saved if they close the app. The warning does not appear if they have performed this action after making the changes. If the switch is off in all instances of the action, the message never appears.|
|_Unlock screen while loading_|Turn on to allow the user to continue to use the app while the flow is running in the background. A spinner will appear to let the user know that something is happening in the background. By default, the loading spinner blocks the screen during data loading.|No|

### Reset

The **Reset** action is used to reset the status of the form to when it was loaded, meaning that it clears all the information the user has added but still displays the information that was set to be shown as default. You can configure which specific fields and resources to reset.

Reset nodes have one input port and one output port. The output port can be connected to other actions that will be performed after the reset is complete.

> Note: Any actions linked to the **Reset** action output port are performed with the data already reset.

The following table describes the **Reset** action available properties:

|**Property**|**Description**|**Required**|
|---|---|---|
|_Description_|Enter an optional description of your action.|No|
|_Reset all fields_|Turn on the switch to reset all eligible fields in the app. When enabled, the _Fields_ property is disabled. By default, the switch is turned on.|No|
|_Fields_|Select the _Component ID_ of the specific fields you want to reset from the drop-down list. Only available when _Reset all fields_ is turned off. See [Field reset behavior](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#field-reset-behavior) for more details.|No|
|_Reset all resources_|Turn on the switch to clear the state of all resources in the app. By default, this switch is turned off. When enabled, the _Resources_ property is disabled.|No|
|_Resources_|Select the specific resources you want to reset from the drop-down list. Only available when _Reset all resources_ is turned off.|No|

#### Field reset behavior

The following components can be reset:

-   **Text input, Text area, Checkbox, Radio, Dropdown, Combobox, Switch** and **Range** components: Values are cleared and returned to their default state.
-   The **File uploader** component: Uploaded files are cleared and the component returns to its initial state.
-   The **Drawing area** component: Drawings are cleared.
-   The **Data grid** component: All rows are cleared or reverted to the default data set, depending on configuration.

> Note: For apps older than version 251.8.0, the **Reset** action now reverts the **Data grid** component rows to default. You must edit the action if you want to change this behavior.

### Field validation

The **Field validation** action allows you to define when and where you want to perform a validation in the app's logic. The validation rules for the field are defined using the **Validation** properties of the component you have selected in the _Fields_ drop-down. See [Validation](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/) for more details and the [Example: Validating date input before sending data](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/validation/#example-validating-date-input-before-sending-data) section for step-by-step guidance.

![Validation action](https://docs-external.u4pp.com/extensions-kit/app-studio/images/validationaction2.png)

Validation nodes have one input port and two output ports:

-   _Green check_ handle for the action executed by default.
-   _Red cross_ handle for the action executed when required field validations, common validation patterns, or errors occur.

The following table describes the **Field validation** action available properties:

|**Property**|**Description**|**Required**|
|---|---|---|
|_Description_|Enter an optional description of your action.|No|
|_Fields_|Select the _Component ID_ of the specific fields you want to validate from the drop-down list.|Yes|

### Toast

The **Toast** action allows you to display information in a toast message. Toast messages are at the top-right corner of the window and are intended to be an unobtrusive way to display information to the user.

Toast nodes have:

-   One input port.
-   No output port or one output port when the _Show action button_ switch is turned on.

The following table describes the **Toast** action available properties:

|**Property**|**Description**|**Required**|
|---|---|---|
|_Description_|Enter an optional description of your action.|No|
|_Variant_|Select the kind of message you want to show. The types of messages are Positive, Negative, Notice, Neutral|Yes|
|_Title_|Enter the title text displayed in the toast. You can reference using Liquid JS. If the text of the _Title_ is too long, only the first three lines are shown in the toast and the text is truncated with an ellipsis (...). Hovering over the text shows the rest of the title.|Yes|
|_Message_|Enter the body of the toast. You can reference using Liquid JS. If the text of the message is too long, only the first two of lines are shown in the toast and the text is truncated with an ellipsis (...). A **Read more** / **Read less** button appears to display and hide the complete text.|No|
|_Show action button_|Sets if the toast shows a button to perform an action. You then link which action to perform in the **Logic map**. When selected, the property _Button text_ is available to configure the name of the button.|No|
|_Close Button_|Sets if a **Close** button is presented in the Toast message. If a **Close** button is present then the toast message remains visible until closed, and if not present then the toast message closes after a six second delay.
Note: Field not available for _Negative_ variant since this variant always has a **Close** button.|No|

### Dialog

The **Dialog** action allows you to include a modal in the app's logic when you need to provide critical information to the user or in cases that require a response from the user, such as a confirmation before the logic continues.

Dialog nodes have only one input port and can have zero, one or two output ports depending on the number of buttons of the dialog.

The **Dialog** action has the following properties:

**Dialog properties**

The following table describes the main properties.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Description_|Enter an optional description of your action.|No|
|_Number of buttons_|Select the number of buttons from the drop-down. See [**How to configure the buttons**](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#how-to-configure-the-buttons-for-the-dialog-action) section for more details.|Yes|
|_Type of dialog_|Select the kind of message you want to show. The types of messages are Success, Error, Information, Warning.|Yes|
|_Heading_|Enter the text displayed in the dialog. You can reference content using Liquid JS.|Yes|
|_Body_|Enter the body of the dialog. You can reference content using Liquid JS.|Yes|

**Primary button / Secondary button properties**

The following table describes the primary and secondary button properties.

|**Property**|**Description**|**Required**|
|---|---|---|
|_Close button_|Turn on to use this button to close the dialog window.|No|
|_Type_|Sets if the button is Highlight or Negative. This sets the button placement with the Highlight button placed to the left of the Negative button.|Yes|
|_Button text_|Mandatory text to be displayed in the button.|Yes|

#### How to configure the buttons for the Dialog action:

-   **Dialog with one button**

To configure the Dialog window with one button:

1.  Choose _One button_ from the _Number of buttons_ drop-down.
2.  The **Primary button** menu becomes available. Open and configure:
    -   By default, the _Close button_ switch is turned on and the _Type_ and _Button text_ are set to read only with the _Highlight Type_ and 'Dismiss' in the _Button text_.
    -   Turn off the _Close button_ switch to change the functionality of the button, the properties become editable and one output port appears to connect any actions you want the end-user to perform when selecting the button. A cross appears in the top-right corner of the dialog to allow the user to close it.

![Dialog one button](https://docs-external.u4pp.com/extensions-kit/app-studio/images/dialogonebutton2.png)

-   **Dialog with two buttons**

To configure the Dialog window with two buttons:

1.  Choose _Two button_ from the _Number of buttons_ drop-down.
2.  The **Primary button** menu becomes available. The _Close button_ switch is disabled and all fields are editable.
3.  The **Secondary button** menu becomes available. Open and configure:
    -   By default, the _Close button_ switch is turned on, the dialog node presents one output port to connect an action for the **Primary button** and all fields are editable.
    -   Turn off the _Close button_ switch to change the functionality of the button, two output ports appear to connect any actions you want the end-user to perform when selecting the button. A cross appears in the top-right corner of the dialog to allow the user to close it.

![Dialog two buttons](https://docs-external.u4pp.com/extensions-kit/app-studio/images/dialogtwobuttons2.png)

> Note: When you change from one button and one output port to two buttons and two output ports, the existing link is kept as the **Primary button**. When you change from two to one, the primary link is kept and the secondary removed.

### Change Screen

The **Change Screen** action allows you to define the navigation between screens in an app that has more than one screen.

The following table describes the **Change Screen** action available properties:

|**Property**|**Description**|**Required**|
|---|---|---|
|_Description_|Enter an optional description of your action.|No|
|_Screen_|Select the screen that the component opens.|Yes|

## Rules for actions

The following rules apply to actions:

-   Concatenation of actions is allowed.
-   Linking an output port to an input port of the same action node is not allowed.
-   Infinite loops with a connection between the last action of a flow and the first one of the same flow is not allowed.
-   When you set **HTTP Request** actions in parallel, all requests are launched simultaneously.
-   If you set **Dialog** or **Toast** actions in parallel, the last one added is shown regardless of how the actions are placed above or below each other in the viewport.

![Actions in parallel](https://docs-external.u4pp.com/extensions-kit/app-studio/images/modalparallel.png)

## Logic control

The following table describes the logic control nodes available:

|**Logic control**|**Events**|**Actions**|**Tabs**|
|---|---|---|---|
|[_If_](https://docs-external.u4pp.com/extensions-kit/app-studio/logic/logic-drawer/#if)|All events|All actions|Logic flow and Logic map|

### If

The **If** logic control allows you to apply a conditional statement to any event or action where a specific outcome is determined by whether the condition is true or false.

It has two output ports:

-   Green output port: Connect to the action you want to be performed if the _Rule_ property is true.
-   Red output port: Connect to the action you want to be performed if the _Rule_ property is false.

The following table describes the **If** logic control available properties:

|**Property**|**Description**|**Required**|
|---|---|---|
|_Description_|Enter an optional description of your action.|No|
|_Rule_|Add a condition or select it from the **Templating** drop-down menu. The rule must return a true or false value. You can use|Yes|
